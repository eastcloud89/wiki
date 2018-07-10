# NSAppTransportSecurity
	<key>NSAppTransportSecurity</key>
	<dict>
	     <!— 어떤 요청이든 허용 하는 부분 —>
	     <key>NSAllowsArbitraryLoads</key>
	     <true/>
	     <!— 어떤 요청이든 허용 하는 부분 —>
	     <key>NSExceptionDomains</key>
	     <dict>
	          <key>localhost</key>
	          <dict>
	          <key>NSTemporaryExceptionAllowsInsecureHTTPSLoads</key>
	          <false/>               
	          <key>NSIncludesSubdomains</key>
	          <true/>
	          <key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
	          <true/>
	          <key>NSTemporaryExceptionMinimumTLSVersion</key>
	          <string>1.0</string>
	          <key>NSTemporaryExceptionRequiresForwardSecrecy</key>
	          <false/>
	          </dict>
	           <key>52.79.70.58</key>
	
	           
	 <dict>
	
	               
	 <!--Include to allow subdomains-->
	
	               
	 <key>NSIncludesSubdomains</key>
	
	               
	 <true/>
	
	               
	 <!--Include to allow HTTP requests-->
	
	               
	 <key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
	
	               
	 <true/>
	
	               
	 <!--Include to specify minimum TLS version-->
	
	               
	 <key>NSTemporaryExceptionMinimumTLSVersion</key>
	
	               
	 <string>TLSv1.1</string>
	            </dict>
	      </dict>
	  </dict>
	</dict>