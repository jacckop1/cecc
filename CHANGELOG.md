# Changelog

## 8.0.2

- Renamed the generated dylib to `WhiteGramArabic-iKiraPlus.dylib`.
- Updated the Mach-O install name to `@rpath/WhiteGramArabic-iKiraPlus.dylib` so the embedded load command and the file name remain consistent.
- Updated GitHub Actions inspection, checksum and artifact paths to the new name.
- No translation hooks, dictionary entries or crash-safety logic were changed.

## 8.0.1

- Changed only the visible `Search settings` label from `البحث في الإعدادات` to `تعريب كيرا بلس`.
- No runtime hooks or crash-safety logic were changed.

## 8.0.0

- Removed every direct read/write of Swift `attributedText` ivars.
- Removed the global `NSBundle` hook restored in v7.
- Removed private `_ASDisplayView` lifecycle interception.
- Kept `UITextView` completely untouched so registration fields and messages are not modified.
- Added a safe pre-render path: exact Whitegram strings are translated when immutable `NSAttributedString` values are constructed.
- Kept stable UIKit hooks for labels, buttons, navigation titles, alerts and search placeholders.
- Added a build-time runtime-safety verifier that rejects the dangerous hooks responsible for the v7 crashes.
- Preserved the 988-entry Arabic dictionary and the current extracted-string audit data.
