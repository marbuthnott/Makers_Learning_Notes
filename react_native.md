# Instagram clone using React Native

**SETTING UP THE ENVIRONMENT**

Setting up the React Native development environment

1. Set up with React Native at [link](https://facebook.github.io/react-native/docs/getting-started).

2. Install Android Studio at [link](https://developer.android.com/studio/install).

3. Setting up the environment variable 'ANDROID_HOME' to it's root 'c:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk'.

4. Added the 'platform_tools' path to the environment variable 'PATH'. By default it is downloaded to 'c:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk\platform-tools'.

**SETTING UP THE PROJECT**

1. Opened remote storage with a `turbo360.co` account. Allows use of CDN for images which is significantly faster than pulling images off the web.

2. Initiated a new project `react-native init instagram_clone`.

3. Setup and open an android virtual device (AVD) via Android Studio.

4. Run `npm install` to complete the dependency install.

5. In the project route run `react-native start` which will initiate the react-native environment.

6. Run `react-native run-android` to load into the virtual world.

7. Create a source folder with `mkdir src`. Within src create a `components` directory, and within components create `container`, `presentation`, and `screens`.

8. Slim down the `App.js` file.

9. Within src create `instaClone.js` and format it.

**IMAGES**

1. Create `assets` folder in the root. Store all your local images here.

2. In src create a `config` folder and create an `index.js` folder. Here write the `export default` function which will add it to the bundle and import them during the build.

### USEFUL CODE

`alert(Dimensions.get("window").width);` - use of alert function to Debug
