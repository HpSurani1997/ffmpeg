## FFMPEG Binaries


https://cocoapods.org/pods/hpsurani-ffmpeg-kit-ios-https


## Modified Podsped of ffmpeg-react-native

require "json"

package = JSON.parse(File.read(File.join(__dir__, "package.json")))

Pod::Spec.new do |s|
  s.name         = package["name"]
  s.version      = package["version"]
  s.summary      = package["description"]
  s.homepage     = package["homepage"]
  s.license      = package["license"]
  s.authors      = package["author"]

  s.platform          = :ios
  s.requires_arc      = true
  s.static_framework  = true

  s.source       = { :git => "https://github.com/arthenica/ffmpeg-kit.git", :tag => "react.native.v#{s.version}" }

  s.default_subspec   = 'https'

  s.dependency "React-Core"

  s.subspec 'https' do |ss|
    ss.source_files = '**/FFmpegKitReactNativeModule.m', '**/FFmpegKitReactNativeModule.h'
    ss.dependency 'hpsurani-ffmpeg-kit-ios-https', "6.0.2"
    ss.ios.deployment_target = '12.1'
  end
end
