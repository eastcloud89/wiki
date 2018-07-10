# selector 공식(selected는 제일 나중에 오게끔 한다!)
	<?xml version="1.0" encoding="utf-8"?>
	<selector xmlns:android="http://schemas.android.com/apk/res/android">
	    <item android:state_pressed="true"
	        android:drawable="@drawable/category_sel"/>
	    <item android:state_activated="true"
	        android:drawable="@drawable/category_sel"/>
	    <item android:state_selected="true"
	        android:drawable="@drawable/category_sel"/>
	</selector>