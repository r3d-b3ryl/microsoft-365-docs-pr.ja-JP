---
title: Windows デバイスで Office 2013 の先進認証を有効にする
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754175"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows デバイスで Office 2013 の先進認証を有効にする

Microsoft Windows コンピューター上の Microsoft Office 2013 では、先進認証がサポートされています。 ただし、有効にするには、次のレジストリ キーを構成する必要があります。

|レジストリ キー|型|値|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> 先進認証は、Office 2016 以降では既に有効になっています。 新しいバージョンの Office では、これらのレジストリ キーを設定する必要はありません。

## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 クライアントの先進認証を有効にする

1. Outlook を終了します。

2. 次のテキストをメモ帳にコピーして貼り付けます。

   ```text
   Windows Registry Editor Version 5.00

   [HKEY_CURRENT_USER\Software\Microsoft\Exchange]
   "AlwaysUseMSOAuthForAutoDiscover"=dword:00000001

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
   "EnableADAL"=dword:00000001
   "Version"=dword:00000001
   ```

3. そのファイルを、ファイル拡張子 .txt の代わりに .reg を使用して、見つけやすい場所に保存します。 たとえば、「 `C:\Data\Office2013_Enable_ModernAuth.reg` 」のように入力します。

4. エクスプローラー (以前の Windows エクスプローラー) を開き、保存した .reg ファイルの場所を参照してダブルクリックします。

5. 表示された **[ユーザー アカウント制御]** ダイアログで、**[はい]** をクリックして、アプリがデバイスに変更を行うことを許可します。

6. **レジストリ エディター** の警告ダイアログが表示されたら、**[はい]** をクリックして変更を承諾します。

レジストリ キーの設定が終わると、Office 2013 アプリが Microsoft 365 で多要素認証 (MFA) を使用するように設定できます。 詳細については、「[多要素認証を設定する](set-up-multi-factor-authentication.md)」を参照してください。

現在、Office クライアント アプリのいずれかにサインイン済みの場合、変更を有効にするには、サインアウトしてサインインし直す必要があります。これを行わない場合、ユーザー情報が確認されるまで、MRU とローミングの設定が使用できなくなります。

## <a name="disable-modern-authentication-on-devices"></a>デバイスで先進認証を無効にする

デバイスで先進認証を無効にする手順は非常によく似ていますが、必要なレジストリ キーが少なく、それらの値を 0 に設定する必要があります。

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

[Outlook でパスワードの入力が求められ、Office 365 への接続に先進認証を使用できない](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)
