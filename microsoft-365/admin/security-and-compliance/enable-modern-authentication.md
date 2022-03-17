---
title: Windows デバイスの Office 2013 の先進認証を有効にする
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
ms.openlocfilehash: c390e3b9858a4d7d8fc37ea5c5e6f1901d5e20fb
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525113"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows デバイスの Office 2013 の先進認証を有効にする

Office 2013 がインストールされている Windows デバイスで先進認証を有効にするには、特定のレジストリ キーを設定する必要があります。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 クライアントの先進認証を有効にする

> [!NOTE]
> 先進認証は Office 2016 クライアントで既に有効になっているため、Office 2016 のレジストリ キーを設定する必要はありません。 
  
Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。 最新の認証を有効にする各デバイスでキーを設定する必要があります。

<br>

****

|レジストリ キー|型|値|
|:---|:---:|---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

次のレジストリ キーを作成または変更して、Outlook EWS や自動検出など、Web サービスに新しい認証方法を使用するように強制します。 ユーザーがモダン認証を使用Outlookユーザーに強制することをお勧めします。

1. Outlook を終了します。

2. レジストリ エディターのバージョンに応じて、次のいずれかの手順を使用してレジストリ エディターをWindows。

   - **Windows 10、Windows 8.1、** およびWindows 8: キーを押Windows R キーを押して 、[実行] **ダイアログ ボックスを** 開きます。 " *regedit.exe*" と入力し、Enter キーを **押します。**
   - **Windows 7:** [**スタート**] をクリックし、検索 *regedit.exe入力して* Enter キーを押 **します。**

3. [レジストリ エディター] で、次のレジストリ サブキーを見つけてクリックします。

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Exchange\
   ```

4. *AlwaysUseMSOAuthForAutoDiscover* キーが見つからない場合は、[編集] メニューの [新規]  をポイントし、[**DWORD 値] を選択します**。 *「AlwaysUseMSOAuthForAutoDiscover」と入力し*、Enter キーを **押します。**

5. *[AlwaysUseMSOAuthForAutoDiscover*] を右クリックし、[変更] を **クリックします。**

6. [値の **データ]** ボックスに **「1」と入力** し、[OK] を **クリックします。**

7. [レジストリ エディター] で、次のレジストリ サブキーを見つけてクリックします。

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\
   ```

8. *EnableADAL キーと* *Version キーが* 既に存在する場合は、必要に応じて値を変更し、レジストリ エディターを終了します。 表示されない場合は、[編集] メニューの [新規]  をポイントし、[**DWORD 値**] を選択して、不足しているキーを作成します。 

9. たとえば、 *EnableADAL キーが* 見つからない場合は、「 *EnableADAL」と入力* し、Enter キーを押 **します。**

10. [ *EnableADAL] を右クリックし*、[変更] を **クリックします。**

11. [値の **データ]** ボックスに **「1」と入力** し、[OK] を **クリックします。**

12. 必要に応じて、Version キーの同じプロセスに従います。 

13. **レジストリ エディターを終了します。**

レジストリ キーを設定したら、2013 デバイス Officeアプリで多要素認証 [(MFA)](set-up-multi-factor-authentication.md) を使用Microsoft 365。 
  
現在、クライアント アプリのいずれかを使ってサインインしている場合、変更を有効にするには、サインアウトしてサインインし直す必要があります。 それ以外の場合、MRU とローミングの設定は、ID が確立されるまで使用できません。
  
## <a name="disable-modern-authentication-on-devices"></a>デバイスで先進認証を無効にする

デバイスで先進認証を無効にするには、デバイスで次のレジストリ キーを設定します。

<br>

****

|レジストリ キー|型|値|
|:---|:---:|---:|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
   
## <a name="related-content"></a>関連コンテンツ

[2 番目の検証Office 2013](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) にサインインする (記事)\
[Outlookを求める](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)メッセージが表示され、モダン認証を使用してパスワードに接続Office 365しない (記事)
