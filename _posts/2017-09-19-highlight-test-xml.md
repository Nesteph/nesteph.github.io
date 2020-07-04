---
layout: post
title: Highlighting XML Code Test
date: '2017-09-18T14:46:00.000-05:00'
author: Steve McMillin
category:
- Demo
tags:
- Code
---

Testing out if xml syntax has issues.
<!--more-->

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>PayloadContent</key>
	<array>
		<dict>
			<key>IPSec</key>
			<dict>
				<key>AuthenticationMethod</key>
				<string>SharedSecret</string>
				<key>LocalIdentifier</key>
				<string>$ID</string>
				<key>LocalIdentifierType</key>
				<string>KeyID</string>
				<key>RemoteAddress</key>
				<string>$HOSTADDRESS</string>
				<key>SharedSecret</key>
				<data>
				$SHAREDSECRET
				</data>
				<key>XAuthEnabled</key>
				<integer>1</integer>
				<key>XAuthName</key>
				<string>$XAUTHUSER</string>
				<key>XAuthPassword</key>
				<string>$XAUTHPASS</string>
			</dict>
			<key>IPv4</key>
			<dict>
				<key>OverridePrimary</key>
				<integer>1</integer>
			</dict>
			<key>PayloadDescription</key>
			<string>Configures VPN settings</string>
			<key>PayloadDisplayName</key>
			<string>VPN</string>
			<key>PayloadIdentifier</key>
			<string>com.apple.vpn.managed.E3C1182E-71F5-4FCC-9C82-24D9ABD6EEB2</string>
			<key>PayloadType</key>
			<string>com.apple.vpn.managed</string>
			<key>PayloadUUID</key>
			<string>3D2399C4-3213-4FB2-989E-CDBD1B957142</string>
			<key>PayloadVersion</key>
			<real>1</real>
			<key>Proxies</key>
			<dict>
				<key>HTTPEnable</key>
				<integer>0</integer>
				<key>HTTPSEnable</key>
				<integer>0</integer>
			</dict>
			<key>UserDefinedName</key>
			<string>$VPNNETWORKDISPLAYNAME</string>
			<key>VPNType</key>
			<string>IPSec</string>
            <key>OnDemandEnabled</key>
            <integer>1</integer>
            <key>OnDemandRules</key>
            <array>
                <dict>
                    <key>Action</key>
                    <string>EvaluateConnection</string>
                    <key>ActionParameters</key>
                    <array>
                        <dict>
                            <key>Domains</key>
                            <array>
                                <string>.com</string>
                                <string>.org</string>
                                <string>.net</string>
                                <string>.int</string>
                                <string>.edu</string>
                                <string>.gov</string>
                                <string>.mil</string>
                                <string>.ca</string>
                                <string>.uk</string>
                                <string>.us</string>
                            </array>
                            <key>DomainAction</key>
                            <string>ConnectIfNeeded</string>
                            <key>RequiredDNSServers</key>
                            <array>
			                        <string>$INTDNS1</string>
			                        <string>$INTDNS2</string>
			                        <string>$INTDNS3</string>
                            </array>
                        </dict>
                    </array>
                </dict>
            </array>
		</dict>
	</array>
	<key>PayloadDisplayName</key>
	<string>$VPNPROFILEDISPLAYNAME</string>
	<key>PayloadIdentifier</key>
	<string>$YOUR-RFQDN.F3303907-813E-4B52-A545-65D7507107BB</string>
	<key>PayloadOrganization</key>
	<string>$YOURORG</string>
	<key>PayloadRemovalDisallowed</key>
	<false/>
	<key>PayloadType</key>
	<string>Configuration</string>
	<key>PayloadUUID</key>
	<string>1754D2E7-25AE-4A8F-8A55-21E92F084A5B</string>
	<key>PayloadVersion</key>
	<integer>1</integer>
</dict>
</plist>
{% endhighlight %}