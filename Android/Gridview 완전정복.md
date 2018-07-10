# Gridview 완전정복
	<GridView
	    android:id="@+id/select_interest_grid_view"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:gravity="center"
	    android:numColumns="4"
	    android:verticalSpacing="@dimen/category_icon_gap"
	    android:layout_marginLeft="3dp"
	    android:layout_marginRight="3dp"
	    android:layout_marginTop="33.2dp"
	    android:choiceMode="multipleChoice"/>
	    
	    
	int rowHeight = (int) getResources().getDimensionPixelSize(R.dimen.item_height_userinfo_interest);
	int jobRowSize = interestList.size() % 4 == 0 ? interestList.size() / 4 : interestList.size() / 4 + 1;
	LinearLayout.LayoutParams jobParams = (LinearLayout.LayoutParams) binding.selectInterestGridView.getLayoutParams();
	jobParams.height = rowHeight * jobRowSize;
	
	
**itemChecked는 계속 데이터 누적!**

**selected는 set해주기 전까지 눌리지 않은 상태다**