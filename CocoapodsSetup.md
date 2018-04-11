# CocoaPods Setup #

Why?

Cocoapods is a system that helps you create the Xcode project (Workspace) that can include other open source projects (Networking, graphics, Auto Layout, etc.).

Manually setting up a project is a good skill to learn, but there are easier ways to get things working.

## Install CocoaPods ##

	$ gem install cocoapods

If you're using the default version of Ruby on macOS, you'll need to use `sudo` for the command.

Otherwise, when you run the above command, it'll fail with something like this error: 

	ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.3.0 directory.

To install CocoaPods, use `sudo` in front of the command, and then type your login password to confirm. Why? This elevates the privileges of the install command, so that it can put files in the protected folder mentioned in the `/Library/Ruby/Gems` path.

	$ sudo gem install cocoapods


## Using Ruby to Install Cocoapods ##

We're using Ruby's `gem` tool to install (or update CocoaPods). Both Sierra and High Sierra should work without any issues, here's how to check your ruby version: 

	$ ruby --version
	ruby 2.3.3p222 (2016-11-21 revision 56859) [universal.x86_64-darwin17]

## Start Using CocoaPods with AlamoFire ##

AlamoFire is a helper for HTTP and web requests in Swift.

<https://github.com/Alamofire/Alamofire>

1. You need an Xcode project to start. Create a project (or use an existing project)
2. Close your Xcode project, as Cocoapods is going to make project changes.
3. Open Terminal to the location of your Xcode project folder
4. Type `pod init` in Terminal

		$ pod init

5. Open the Podfile and edit it look like the following 

		platform :ios, '10.3'
		use_frameworks!
		
		target 'GithubProfile' do

		end

The lines started with `#` are comments, and since we're using Swift, you'll need `use_frameworks!`

6. Add AlamoFire's current version (use version 4.7 with Xcode 9.3) by adding the line `pod 'Alamofire', '~> 4.7'` inside the `target area`, see below:


		platform :ios, '10.3'
		use_frameworks!
		
		target 'GithubProfile' do		
		  pod 'Alamofire', '~> 4.7'
		end

6. Run CocoaPods install

		$ pod install

7. Depending on how old your CocoaPod install is, you might need to try the `update` command to get the version numbers to work. If you see an error like:

		[!] CocoaPods could not find compatible versions for pod "Alamofire":
		  In Podfile:
		    Alamofire (~> 4.7)
		
		None of your spec sources contain a spec satisfying the dependency: `Alamofire (~> 4.7)`.
		
		You have either:
		 * out-of-date source repos which you can update with `pod repo update` or with `pod install --repo-update`.
		 * mistyped the name or version.
		 * not added the source repo that hosts the Podspec to your Podfile.
		
		Note: as of CocoaPods 1.0, `pod repo update` does not happen on `pod install` by default.

## Troubleshoot Your CocoaPods

Sometimes things fail, and you need to try the commands again. I find that either clearing the cache, making sure the Podfile changes are saved, and then doing an update (or an install command) fixes the problems.

Clear cached files to start over

		$ pod cache clear --all

Update Cocoapods

		$ pod update

## Using Alamofire ##

1. Open your Workspace file that was generated `GithubProfile.xcworkspace`

2. Add the statement at the top of the "ViewController.swift" file

		import Alamofire

3. Create a new function

	    func searchForUserAlamo(username: String) {
	        
	        Alamofire.request(URL(string: "https://api.github.com/users/\(username)")!)
	            .validate()
	            .response { (response) in
	            
	            print("Request: \(response.request)")
	            print("Response: \(response.response)")
	            print("Error: \(response.error)")
	            
	            if let data = response.data {
	                do {
	                    let json = try JSONSerialization.jsonObject(with: data, options: [])
	                    print(json)
	                    
	                    // Try to decode a GithubProfile struct
	                    let decoder = JSONDecoder()
	                    let profile = try decoder.decode(GithubProfile.self, from: data)
	                    
	                    self.updateUI(profile: profile)
	                } catch {
	                    print("Error: ", error)
	                }
	
	            }
	        }
	    }



# Resources #

* [Getting Started with CocoaPods](https://guides.cocoapods.org/using/getting-started.html)
* [Alamofire](https://github.com/Alamofire/Alamofire)
* [Alamofire Usage](https://github.com/Alamofire/Alamofire/blob/master/Documentation/Usage.md)
* Checkout another Cocoapod for animations: [Pop](https://github.com/facebook/pop)



