# realm browser 사용법
## android
설정

    private File EXPORT_REALM_PATH = Environment.getExternalStoragePublicDirectory(Environment.DIRECTORY_DOWNLOADS);
    private String EXPORT_REALM_FILE_NAME = "pollide.realm";
    private String IMPORT_REALM_FILE_NAME = "default.realm"; // Eventually replace this if you're using a custom db name

실행    

	File exportRealmFile;
	Log.d("MainActivity", "Realm DB Path = " + realm.getPath());
	
	EXPORT_REALM_PATH.mkdirs();
	
	// create a backup file
	exportRealmFile = new File(EXPORT_REALM_PATH, EXPORT_REALM_FILE_NAME);
	
	// if backup file already exists, delete it
	exportRealmFile.delete();
	
	// copy current realm to backup file
	realm.writeCopyTo(exportRealmFile);
	
	String msg = "File exported to Path: " + EXPORT_REALM_PATH + "/" + EXPORT_REALM_FILE_NAME;
	Toast.makeText(this.getApplicationContext(), msg, Toast.LENGTH_LONG).show();
	Log.d("MainActivity", msg);

확인

	run 누르고, command 창 열고,
	
	adb pull /storage/emulated/0/Download/pollide.realm