# iOS-Simulator-SDK


Please find the attached SDK for Simulator supported SDK and here are the installation instructions.

Add below pods to your Podfile. </br>
```
pod 'Socket.IO-Client-Swift'
pod 'lottie-ios'
```

1. Copy “ShuftiPro.framework” into your project folder. </br>
2. In Xcode select your project -> your project under TARGETS -> General -> Embedded Binaries </br>
3. Make sure the framework is added as Embed & Sign </br>
4. Add “ShuftiPro.framework” in Embedded Binaries </br>


Add these lines to the end of Podfile

```
post_install do |installer|

  installer.pods_project.targets.each do |target|

    if ['Socket.IO-Client-Swift', 'Starscream' ,'lottie-ios'].include? target.name

      target.build_configurations.each do |config|

          config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'

      end

    end

  end

end
```