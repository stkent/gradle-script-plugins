# gradle-script-plugins

Gradle script plugins used to configure Android library projects.

# Usage

Define the following extra properties for the Project object in your `build.gradle` file:

```groovy
ext {
    // Library info:
    libraryVersion = '1.0.0'
    libraryName = 'LibraryName'
    libraryGroupId = 'com.example'
    libraryArtifactId = 'library-name'
    libraryDescription = 'The best thing since sliced arrays.'
    libraryInceptionYear = '2016'
    libraryGitHubRepoName = 'bhorseman/LibraryName'
    libraryGitHubUrl = "https://github.com/${libraryGitHubRepoName}"
    libraryIssueTrackerUrl = "${libraryGitHubUrl}/issues"
    libraryWebsiteUrl = libraryGitHubUrl
    libraryLabels = ['best', 'sliced', 'arrays']
    libraryLicenseName = 'Apache License Version 2.0'
    libraryLicenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.html'

    // Developer info:
    developerId = 'bhorseman'
    developerName = 'BoJack Horseman'
    developerEmail = 'bojack@horseman.com'

    // Hosting info:
    bintrayRepo = 'bojack-libs'
}
```

## Android

Make sure your `buildscript` and `repository` blocks contain the following information:

```groovy
buildscript {
    repositories {
        jcenter()

        maven {
            url "https://plugins.gradle.org/m2/"
        }
    }

    dependencies {
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.6'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'
    }
}

repositories {
    jcenter()
}
```

Add [the following lines](https://docs.gradle.org/current/userguide/plugins.html#sec:using_plugins) _below_ the extra properties defined above:

```groovy
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/android-bintray.gradle'
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/android-install.gradle'
```

## Java

Add the following lines _below_ the extra properties defined above:

```groovy
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/android-bintray.gradle'
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/android-install.gradle'
```

Enjoy responsibly.