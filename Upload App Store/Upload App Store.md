# Tạo App trên App Store

- [Tạo App trên App Store](#t%e1%ba%a1o-app-tr%c3%aan-app-store)
  - [Tạo key trong keychain](#t%e1%ba%a1o-key-trong-keychain)
  - [Create Certificates, Identifiers & Profiles](#create-certificates-identifiers--profiles)
    - [Create Certificates](#create-certificates)
    - [Create Identifiers](#create-identifiers)
    - [Create Devices](#create-devices)
    - [Create Profiles](#create-profiles)
  - [Connect App Store](#connect-app-store)
  - [Push App to Store](#push-app-to-store)
  - [Note](#note)
    - [Update App](#update-app)
    - [Debug app on Other Mac](#debug-app-on-other-mac)

## Tạo key trong keychain

- Keychain Access/ Certificate Assistant/ Request Certificate from certificate Authority...

- Paste Login Email
[x] Save To Disk

- Tạo ra file: *.certSigningRequest

![create cer](create_cert.png)

## Create Certificates, Identifiers & Profiles

Truy cập:
<https://developer.apple.com/account/resources/profiles/list>

![Certificates_Identifiers_Profiles](Certificates_Identifiers_Profiles.png)

### Create Certificates

Chứng chỉ cho App. Có thể dùng nhiều App

- Nhấp (+)
- Create a New Certificate:
  - Apple Distribution (Xcode 11 về trước)
  - iOS App Development (Sau này)
- Nhấn Continue
  - Choose File: chọn file *.certSigningRequest
- Nhấn Continue
  - Nhấn Download: file *.cer
  
- Chạy file .cer trong Keychain
- Export Certificate vừa tạo: file .p12
(Share file cho Thành viên trong nhóm)

### Create Identifiers

Id cho App.

- Nhấp (+)
- Register a New Identifier
  - App IDs (Tạo App id)
- Nhấp Continue
  - Bundle ID: App Id (Bundle Indentifier)
- Nhấp Register

### Create Devices

Add Devices UID, if want debug

### Create Profiles

Development or Distribution Profile

## Connect App Store

goto App Store Connect: <https://appstoreconnect.apple.com/WebObjects/iTunesConnect.woa/ra/ng/app>

![app store connect overview](AppStoreConnectOverview.png)

- Create App. Click (+)
- App Store > App Infomation: Privacy Policy URL (must be exist page)
- Create VERSION OR PLATFORM:
  - Included Assets (must have)
  - General App Information > App Store Icon (must have)

## Push App to Store

![Organizer](Organizer.png)

- Xcode > Product > Archive
- View All Archives: Window > Organizer
  - Click Distributte App

## Note

### Update App

Delete exist Certificates, Indentifiers, Profiles

### Debug app on Other Mac

![profile on app](Profile_on_project.png)

- Delete related app Certificates on app:
    > Keychain Access > My Certificates
- Install Profile Manager <https://github.com/Hipo/ProvisioningProfileManager>. Delete exist app Profiles: Profile Manager
- Share files:
  - Export Certificate: file *.p12
  - Export Profiles(only install 1 Profile for other Mac): file *.mobileprovision
- Install 2 shared files (.p12, .mobileprovision)

---
