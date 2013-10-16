Android-GallaryViewDemo
=======================
This application will show how to add grid view in an application .<br>
All you  need is additional adapter that populates the grid elements .<br>
Steps to follow are as follows : <br>
<br>
Step 1 : Create the Layout for the main Activity containing a gridView.<br>
Step 2 : Create the adapter class “ImageAdapter.java”.<br>
Step 3 : Create the main Activity class . “MainActivity.java”<br>
<br>

____________________________________________________________________________________________________________________________________________________________
Step 1: Create the Layout for the main Activity containing a gridView.
<GridView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/gridView"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:columnWidth="90dp"
    android:gravity="center"
    android:horizontalSpacing="10dp"
    android:numColumns="auto_fit"
    android:stretchMode="columnWidth"
    android:verticalSpacing="10dp" >

</GridView>

____________________________________________________________________________________________________________________________________________________________
Step 2 : Create the adapter class “ImageAdapter.java”


	private int[] images = { R.drawable.image1, R.drawable.image2,
			R.drawable.image3, R.drawable.image4, R.drawable.image5,
			R.drawable.image6, R.drawable.image7, R.drawable.image8,
			R.drawable.image9, R.drawable.image10, R.drawable.image11,
			R.drawable.image12 };


	@Override
	public View getView(int position, View convertView, ViewGroup parent) {
		ImageView imageView = new ImageView(mContext);
		imageView.setImageResource(images[position]);
		imageView.setScaleType(ImageView.ScaleType.CENTER_CROP);
		imageView.setLayoutParams(new GridView.LayoutParams(210, 210));
		return imageView;
	}

____________________________________________________________________________________________________________________________________________________________
Step 3 : Create the main Activity class . “MainActivity.java”

		GridView gridView = (GridView) findViewById(R.id.gridView);
		gridView.setAdapter(new ImageAdapter(this));
__________________________________________________________________________________________________________________________________________________________
