# Lottie for Android

Lottie is a mobile library for Android and iOS that parses Adobe After Effects animations exported as json with Bodymovin and renders them natively on mobile and on the web.

For the first time, designers can create and ship beautiful animations without an engineer painstakingly recreating it by hand. They say a picture is worth 1,000 words so here are 13,000:

# View full documentation on http://airbnb.io/lottie/

You can download free Lottie Animation json file for your App form https://www.lottiefiles.com/?page=1

![alt tag](https://github.com/abhishekkrsoni/LottieDemo/blob/master/lottieDemo.gif "Demo of this App")

# Steps for using Lottie in your Android Project 

Step:- 1
  Add the dependency to your project build.gradle file:

dependencies {
    ...
    compile 'com.airbnb.android:lottie:2.5.1'
    ...
}

Step:- 2
  Loading an Animation
  
Download json file example animated_indonesian_first_president.json
Now create assets folder New -> Folder -> Assets Folder   and paste json file on it.

Step:- 3
  Open activity_main.xml and paste this inside parent layout
   
    ...
    <com.airbnb.lottie.LottieAnimationView
        android:id="@+id/animation_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        app:lottie_autoPlay="true"
        app:lottie_fileName="animated_indonesian_first_president.json"
        app:lottie_loop="true"/>
     ...
       
Step:- 4
    Open MainActivity.java and paste this inside onCreate(...)

    ...
    LottieAnimationView lottieAnimationView;
    Button button;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        ...
        lottieAnimationView = (LottieAnimationView) findViewById(R.id.animation_view);
        button = (Button) findViewById(R.id.button);
        button.setText(getString(R.string.pause));
        ...
    }

    
    public void onClick(View v) {
        if (lottieAnimationView.isAnimating()) {
            lottieAnimationView.cancelAnimation();
            button.setText(getString(R.string.play));
        } else {
            lottieAnimationView.playAnimation();
            button.setText(getString(R.string.pause));
        }
    }
  
# Now U r done with Lottie

