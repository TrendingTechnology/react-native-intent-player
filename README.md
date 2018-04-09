# React Native: Native Player

[![github home](https://img.shields.io/badge/gaetanozappi-react--native--player-blue.svg?style=flat-square)](https://github.com/gaetanozappi/react-native-player)
[![github issues](https://img.shields.io/github/issues/gaetanozappi/react-native-player.svg?style=flat-square)](https://github.com/gaetanozappi/react-native-player/issues)

-   [Usage](#usage)
-   [License](#license)

### Android

Add `react-native-player` to your `./android/settings.gradle` file as follows:

```diff
...
include ':app'
+ include ':react-native-player'
+ project(':react-native-player').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-player/android/app')
```

Include it as dependency in `./android/app/build.gradle` file:

```diff
dependencies {
    ...
    compile "com.facebook.react:react-native:+"  // From node_modules
+   compile project(':react-native-player')
}
```

Finally, you need to add the package within the `ReactInstanceManager` of your
MainActivity (`./android/app/src/main/java/your/bundle/MainActivity.java`):

```java
import com.reactlibrary.PlayerPackage;  // <---- import this one
...
@Override
protected List<ReactPackage> getPackages() {
    return Arrays.<ReactPackage>asList(
        new MainReactPackage(),
        new PlayerPackage()  // <---- add this line
    );
}
```

After that, you will need to recompile
your project with `react-native run-android`.

## Usage

```javascript
import Player from 'react-native-player';
```

- API Way

```javascript
Player.play(url).then(a => {
  console.log(a);
}).catch(e => console.log(e));
```

## License
The MIT License
