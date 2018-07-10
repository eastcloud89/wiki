# iOS webview 완전정복
	//
	//  ViewController.swift
	//  test
	//
	//  Created by 굿윌헌팅 on 2017. 7. 1..
	//  Copyright © 2017년 굿윌헌팅. All rights reserved.
	//
	
	import UIKit
	
	class ViewController: UIViewController, UIWebViewDelegate {
	    
	    @IBOutlet weak var webView: UIWebView!
	    @IBOutlet weak var splashImageView: UIImageView!
	    @IBOutlet weak var activityIndicator: UIActivityIndicatorView!
	    
	    override func viewDidLoad() {
	        super.viewDidLoad()
	        // Do any additional setup after loading the view, typically from a nib.
	    
	
	        webView.allowsInlineMediaPlayback = true
	        webView.mediaPlaybackRequiresUserAction = false
	        webView.mediaPlaybackAllowsAirPlay = true
	        
	        webView.scrollView.showsVerticalScrollIndicator = false
	        webView.scrollView.showsHorizontalScrollIndicator = false
	        webView.scrollView.bounces = false
	        webView.delegate = self
	
	        let swipeLeftRecognizer = UISwipeGestureRecognizer(target: self, action: #selector(handleSwipe(recognizer:)))
	        let swipeRightRecognizer = UISwipeGestureRecognizer(target: self, action: #selector(handleSwipe(recognizer:)))
	        swipeLeftRecognizer.direction = .left
	        swipeRightRecognizer.direction = .right
	        webView.addGestureRecognizer(swipeLeftRecognizer)
	        webView.addGestureRecognizer(swipeRightRecognizer)
	        webView.isUserInteractionEnabled = true
	        
	        let eURL = URL(string: "http://beauteach.com")
	        let eURLRequest = URLRequest(url: eURL!)
	        webView.loadRequest(eURLRequest)
	        
	    }
	
	    override func didReceiveMemoryWarning() {
	        super.didReceiveMemoryWarning()
	        // Dispose of any resources that can be recreated.
	    }
	    
	    func webViewDidStartLoad(_ webView: UIWebView) {
	        activityIndicator.startAnimating();
	    }
	    
	    func webViewDidFinishLoad(_ webView: UIWebView) {
	        activityIndicator.stopAnimating();
	        guard let _ = splashImageView else {
	            return
	        }
	        splashImageView.removeFromSuperview()
	    }
	    
	    func handleSwipe(recognizer: UISwipeGestureRecognizer) {
	        if (recognizer.direction == .left) {
	            if webView.canGoForward {
	                webView.goForward()
	            }
	        }
	        
	        if (recognizer.direction == .right) {
	            if webView.canGoBack {
	                webView.goBack()
	            }
	        }
	    }
	}
	
