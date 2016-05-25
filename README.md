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

Add [the following lines](https://docs.gradle.org/current/userguide/plugins.html#sec:using_plugins) below the block above:

```groovy
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/bintray.gradle'
apply from: 'https://raw.githubusercontent.com/stkent/gradle-script-plugins/master/install.gradle'
```

Enjoy responsibly.