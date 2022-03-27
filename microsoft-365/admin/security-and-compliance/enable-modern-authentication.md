---
title: 2013 年Officeデバイスでモダン認証Windowsする
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013 がインストールされているデバイスの最新の認証を有効にするレジストリ キーの設定方法を説明します。
ms.openlocfilehash: 468658c3b346c7923937ff9595699a20306ed6a9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754175"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>2013 年Officeデバイスでモダン認証Windowsする

Microsoft Office 2013 on Microsoft Windowsモダン認証がサポートされています。 ただし、有効にするには、次のレジストリ キーを構成する必要があります。

|レジストリ キー|型|値|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> 最新の認証は、2016 以降Officeで有効になっています。 以降のバージョンのレジストリ キーを設定する必要Office。

## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 クライアントの先進認証を有効にする

1. Outlook を終了します。

2. 次のテキストをコピーして、次のテキストをメモ帳。

   ```text
   Windows Registry Editor Version 5.00

   [HKEY_CURRENT_USER\Software\Microsoft\Exchange]
   "AlwaysUseMSOAuthForAutoDiscover"=dword:00000001

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
   "EnableADAL"=dword:00000001
   "Version"=dword:00000001
   ```

3. 見つけやすい場所にファイル拡張子 .reg .txtファイルを保存します。 たとえば、`C:\Data\Office2013_Enable_ModernAuth.reg` などです。

4. エクスプローラー (以前は Windows エクスプローラー) を開き、保存した .reg ファイルの場所を参照し、ダブルクリックします。

5. 表示される **[ユーザー アカウント制御]** ダイアログで、[ **は** い] をクリックして、アプリがデバイスに変更を加えるのを許可します。

6. 表示される **[レジストリ エディター] 警告** ダイアログで、[はい **] をクリック** して変更を受け入れます。

レジストリ キーを設定したら、複数要素認証 (MFA) を使用Office 2013 アプリを設定Microsoft 365。 詳細については、「[多要素認証を設定する](set-up-multi-factor-authentication.md)」を参照してください。

現在、任意のクライアント アプリにサインインしているOffice、変更を有効にするためにサインアウトしてサインインする必要があります。 それ以外の場合、MRU とローミングの設定は、ID が確立されるまで使用できません。

## <a name="disable-modern-authentication-on-devices"></a>デバイスで先進認証を無効にする

デバイスで最新の認証を無効にする手順は非常に似ていますが、必要なレジストリ キーは少なく、値を 0 に設定する必要があります。

|レジストリ キー|型|値|
|---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|

```text
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Exchange]
"AlwaysUseMSOAuthForAutoDiscover"=dword:00000000

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
"EnableADAL"=dword:00000000
```

## <a name="related-content"></a>関連コンテンツ

[第 2 検証方法を使用して Office 2013 にサインインする](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlookを求めるメッセージが表示され、モダン認証を使用してパスワードに接続Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)
