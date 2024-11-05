---
title: Page of fun
deprecated: false
hidden: true
metadata:
  robots: index
---
# **Mac Authenticator Automated Device Enrollment Guide**

## **Overview**

* Jamf Pro setup

  * Create MDM Server

  * Create Configuration Profiles

  * Create PreStage Enrollment

## **Deploying TruU with JAMF Pro**

**Step 1:** Sign into your Jamf Pro account [https://{user.domain}.](https://truunfr.jamfcloud.com/)[jamfcloud.com](//jamfcloud.com)

**Step 2:** Go to "Settings", then navigate to the "Automated device enrollment" to create a new MDM server integration

<Image align="center" className="border" border={true} src="https://files.readme.io/e05999b-image.png" />

<br />

**Step 3:** Setup new instance of MDM server (Choose server token file obtained from Apple Business Manager as described in step 4 in the Apple Business Manager section)

<Image align="center" className="border" border={true} src="https://files.readme.io/c113624-image.png" />

<br />

**Step 4:** Setup Configuration Profiles

**4-a:** Go to "Computers", then navigate to "Configuration Profiles"

<Image align="center" className="border" border={true} src="https://files.readme.io/c353b3f-image.png" />

<br />

**4-b:** Create "Account Provisioning Profile"

**4-b-i:** Click the **+ New** button to create new profile

<Image align="center" className="border" border={true} src="https://files.readme.io/4e567a4-image.png" />

<br />

**4-b-ii:** Provide a *name* for the new configuration profile

<Image align="center" className="border" border={true} src="https://files.readme.io/9930ec6-image.png" />

<br />

**4-b-iii:** Open "Application & Custom Settings” and click **Upload**

<Image align="center" className="border" border={true} src="https://files.readme.io/91fd4a5-image.png" />

<br />

**4-b-iv:** Define Property List (PLIST) for the Configuration Profile

<Image align="center" className="border" border={true} src="https://files.readme.io/af1da3f-image.png" />

<br />

* Create Preference Domain for ai.truu.ma.dep with the following PLIST:

```xml
<?xml version="1.0" encoding="UTF-8"?> <!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> <plist version="1.0"> <dict>     <key>createAdminAccount</key>     <true/> </dict> </plist>
```

* You will see the following in your profile:

<Image align="center" className="border" border={true} src="https://files.readme.io/db806c6-image.png" />

<br />

**4-c:** Create Application Provisioning Profile

**4-c-i:** Follow steps i – iii for part b above to add the Application Provisioning Profile

**4-c-ii:** Enter *ai.truu.ma.configuration* as the Preference Domain

**4-c-iii:** To create the PLIST, you will need to convert your "application.config" file to a PLIST by replacing the “CHANGE IT” variables with the the values from your config file

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>allowPasswordSync</key>
	<true/>
	<key>canUnenroll</key>
	<true/>
	<key>enableAdminAccess</key>
	<true/>
	<key>domain</key>
	<string>c2</string>
	<key>idsDomainLookup</key>
	<string>https://global-stage.platform.truu.ai/api/v1/public/fqdn/{CHANGE IT}</string>
	<key>oAuthClientId</key>
	<string>{CHANGE IT}</string>
	<key>oAuthClientSecret</key>
	<string>{CHANGE IT}</string>
	<key>oAuthScope</key>
	<string>tenant-management-api-agent</string>
	<key>ssoRedirectionURLs</key>
	<array>
		<string>{CHANGE IT}</string>
	</array>
	<key>authPluginSettings</key>
	<dict>
		<key>enableLoginWindow</key>
		<true/>
	</dict>
	<key>accountLockOverride</key>
	<dict>
		<key>maxFailedLoginAttempts</key>
		<integer>10</integer>
		<key>minutesUntilFailedLoginReset</key>
		<integer>10</integer>
		<key>shouldLockScreenOnAccountLock</key>
		<true/>
	</dict>
</dict>
</plist>
```

**4-d:** Create Configuration to Enable SSO

**4-d-i:** Scroll to “Single Sign-On Extensions” and click the **+ Add** button

<Image align="center" className="border" border={true} src="https://files.readme.io/636753e-image.png" />

<br />

**4-d-ii:** Enter the following:

* **Payload Type –** *SSO*
* **Extension Identifier –** *com.truu.LoginHost.SSO*
* **Team Identifier –** *VGJPA2G633*
* **Sign-on Type –** *Credential*
* \*\*Realm\*\* – \_Company Kerberos Ream\_ (e.g. \{\[domain.com]\(//domain.com)   })
* \*\*Hosts\*\* – \_Company resources domains\_ (e.g. \{\[domain.com]\(//domain.com)   })

<Image align="center" className="border" border={true} src="https://files.readme.io/6384e5f-image.png" />

<br />

**4-e:** Apply Scope for Provisioning Profiles (as needed)

<Image align="center" className="border" border={true} src="https://files.readme.io/c8a5a42-image.png" />

<br />

**Step 5:** Configure PreStage Enrollments

**5-a:** Go to "Computers", then select "PreStage Enrollments"

<Image align="center" className="border" border={true} src="https://files.readme.io/66961fc-image.png" />

<br />

**5-b:** Setup new PreStage Enrollment

**5-c:** General settings (MDM server, Setup Assistant Options, etc.)\
Note: TruU agent is responsible for local account creation during enrollment process. Account creation from MDM setting should be skipped

<Image align="center" className="border" border={true} src="https://files.readme.io/bc19867-image.png" />

<br />

**5-d:** Select the Configuration Profiles that were created above

<Image align="center" className="border" border={true} src="https://files.readme.io/5b31e6b-image.png" />

<br />

**5-e:** Define the Distribution Point for the Enrollment Package

<Image align="center" className="border" border={true} src="https://files.readme.io/eb40ff2-image.png" />

<br />

You’re all set! Go back to iOS Apple Configuration Application and start provisioning for new machines