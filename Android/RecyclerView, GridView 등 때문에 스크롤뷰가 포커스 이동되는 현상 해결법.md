# RecyclerView, GridView 등 때문에 스크롤뷰가 포커스 이동되는 현상 해결법
	mLayoutScrollView = (ScrollView) view.findViewById(R.id.make_question_scroll_view);
	
	mLayoutScrollView.setDescendantFocusability(ViewGroup.FOCUS_BEFORE_DESCENDANTS);
	mLayoutScrollView.setFocusable(true);
	mLayoutScrollView.setFocusableInTouchMode(true);
	
## 설명
### mLayoutScrollView.setDescendantFocusability(ViewGroup.FOCUS_BEFORE_DESCENDANTS);
-> 자식들보다 먼저 포커스를 얻는다

### mLayoutScrollView.setFocusable(true);
-> 포커스를 받을 수 있게 한다

### mLayoutScrollView.setFocusableInTouchMode(true);
-> 터치모드에서 포커스를 받을 수 있게 한다.

##기타

	mLayoutScrollView.setOnTouchListener(new View.OnTouchListener() {
		    @Override
		    public boolean onTouch(View v, MotionEvent event) {
		        v.requestFocusFromTouch();
		        getActivity().getWindow().setSoftInputMode(WindowManager.LayoutParams.SOFT_INPUT_STATE_ALWAYS_HIDDEN);
		        InputMethodManager imm = (InputMethodManager) getActivity().getSystemService(Context.INPUT_METHOD_SERVICE);
		        imm.hideSoftInputFromWindow(getActivity().getCurrentFocus().getWindowToken(), 0);
		        return false;
		    }
	});

### v.requestFocusFromTouch();
-> 자식들이 터치 되었을 때 포커스를 얻을 수 있도록 한다.
-> return false를 통해 본인은 포커스를 얻지 않는다
### 키보드 내리기
	getActivity().getWindow().setSoftInputMode(WindowManager.LayoutParams.SOFT_INPUT_STATE_ALWAYS_HIDDEN);
	InputMethodManager imm = (InputMethodManager) getActivity().getSystemService(Context.INPUT_METHOD_SERVICE);
	imm.hideSoftInputFromWindow(getActivity().getCurrentFocus().getWindowToken(), 0);
-> 키보드를 내릴 수 있도록 한다.	