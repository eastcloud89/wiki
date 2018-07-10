# iOS 리뷰받기
## 제약사항
**iOS 리뷰 다이얼로그는 iOS 10.3부터 가능하며 xcode 8.3 부터 가능하다!**

왜냐하면, xcode 8.2.1 에서는 latest sdk가 10.2 이기 때문에 지원되지 않는다
## 참고링크
[참고](https://www.behradbagheri.com/boringb-tutorials/2017/4/a-proper-way-to-request-review-using-skstorereviewcontroller-in-ios-103-and-higher)
## 구현방법
AppDelegate

 	func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {

        incrementAppRuns()
        return true
 }

B2_ReviewRequest.swift

	//
	//  B2_ReviewRequest.swift
	//
	//  Created by Behrad Bagheri on 4/7/17.
	//  Copyright © 2017 BehradBagheri. All rights reserved.
	
	import Foundation
	import StoreKit
	
	
	let runIncrementerSetting = "numberOfRuns"  // UserDefauls dictionary key where we store number of runs
	let minimumRunCount = 5                     // Minimum number of runs that we should have until we ask for review
	
	
	func incrementAppRuns() {                   // counter for number of runs for the app. You can call this from App Delegate
	    
	    let usD = UserDefaults()
	    let runs = getRunCounts() + 1
	    usD.setValuesForKeys([runIncrementerSetting: runs])
	    usD.synchronize()
	    
	}
	
	func getRunCounts () -> Int {               // Reads number of runs from UserDefaults and returns it.
	    
	    let usD = UserDefaults()
	    let savedRuns = usD.value(forKey: runIncrementerSetting)
	    
	    var runs = 0
	    if (savedRuns != nil) {
	        
	        runs = savedRuns as! Int
	    }
	    
	    print("Run Counts are \(runs)")
	    return runs
	    
	}
	
	func showReview() {
	    
	    let runs = getRunCounts()
	    print("Show Review")
	    
	    if (runs > minimumRunCount) {
	        
	        if #available(iOS 10.3, *) {
	            print("Review Requested")
	            SKStoreReviewController.requestReview()
	            
	        } else {
	            // Fallback on earlier versions
	        }
	        
	    } else {
	        
	        print("Runs are now enough to request review!")
	           
	    }
	    
	}