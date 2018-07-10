# 액티비티 실행 시 EditText에 포커스 주지 않는 방법
<LinearLayout>
	android:focusable="true"
	android:focusableInTouchMode="true"
	
또는
	
oncreate

	this.getWindow().setSoftInputMode(WindowManager.LayoutParams.SOFT_INPUT_STATE_ALWAYS_HIDDEN);
	