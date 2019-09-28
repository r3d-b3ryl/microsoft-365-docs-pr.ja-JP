---
title: Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Microsoft 365 Business の保護機能が Intune 設定にマップされる方法について説明します。 サブスクリプションでは、Intune の設定を変更するためのライセンスが提供されます。
ms.openlocfilehash: 316dc8efbe69057f049bf8fadd3c3f41c358a33e
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287966"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法

## <a name="android-and-ios-application-protection-settings"></a>Android および iOS アプリケーションの保護の設定

次の表では、Android および iOS アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を検索するには、Microsoft 365 Business 管理者の資格情報を使用してサインインしている間に、[**管理センター**]、[ **intune**] の順に移動します。
  
 **重要:** Microsoft 365 Business サブスクリプションでは、すべての Intune 設定を変更するためのライセンスが提供されています。 [開始するには、「Intune の概要」を参照し](https://docs.microsoft.com/intune/introduction-intune)てください。
  
選択するポリシーの名前をクリックし (たとえば、Android のアプリケーション ポリシー)、[ **ポリシー設定**] を選びます。
  
[ **デバイスの紛失または盗難時の作業ファイルの保護**] の設定
  
|**Android または iOS のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|アクティブでない状態が指定の日数続いたデバイスから作業ファイルを削除する  <br/> |アプリのデータがワイプされるまでのオフライン期間 (日数)  <br/> |
|OneDrive for Business に作業ファイルを保存するように強制する  <br/> OneDrive for Business だけが許可されることに注意してください  <br/> |会社のデータを保存できるストレージ サービスの選択  <br/> |
|||
   
[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] の設定
  
|**Android または iOS のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|アクティブでない状態が指定の日数続いたデバイスから作業ファイルを削除する  <br/> |アプリのデータがワイプされるまでのオフライン期間 (日数)  <br/> |
|OneDrive for Business に作業ファイルを保存するように強制する  <br/> OneDrive for Business だけが許可されることに注意してください  <br/> |会社のデータを保存できるストレージ サービスの選択  <br/> |
|作業ファイルの暗号化  <br/> |アプリケーション データを暗号化する  <br/> |
|[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] の設定 <br/> ||
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> | アクセスのために PIN を要求する  <br/>  これにより、以下も設定されます。  <br/> **単純な PIN を許可する**: **はい** <br/> **PIN の長さ**: 4  <br/> **PIN の代わりに指紋認証を許可する**: **はい** <br/> **デバイス PIN が管理されている場合にアプリ PIN を無効にする**: **いいえ** <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする (PIN が必要ない場合は無効)  <br/> |PIN をリセットするまでの試行回数  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある (PIN が必要ない場合は無効)  <br/> | (分数) 後にアクセス要件を再確認する  <br/>  これにより、以下も設定されます。  <br/> **タイムアウト**: 分数  <br/>  これは、Microsoft 365 Business で設定したものと同じ分数です。  <br/> **オフラインの猶予期間**: 720 分 (既定値)  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する  <br/> |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  <br/> | 他のアプリとの間で切り取り、コピー、貼り付けを制限する  <br/>  Microsoft 365 Business のオプションが [ **オン**] に設定されている場合、Intune の次の 3 つのオプションも [ **すべてのアプリ**] に設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする** <br/> **このアプリで他のアプリからデータを受信できるようにする** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する** <br/>  Microsoft 365 Business のオプションが [ **オン**] に設定されている場合、Intune の以下のすべてのオプションが次のように設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする**: **ポリシーで管理されているアプリ** <br/> **このアプリで他のアプリからデータを受信できるようにする**: **すべてのアプリ** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する**: **貼り付けを使用する、ポリシーで管理されているアプリ** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 アプリの保護の設定

次の表では、Windows 10 アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を検索するには、Microsoft 365 Business 管理者の資格情報を使用してサインインしている間に、 [Azure portal](https://portal.azure.com)に移動し、[**その他のサービス**] を選択して、**フィルター**に Intune を入力し、[ **intune App Protection** \> **] を選択します。アプリポリシー**。
  
 **重要**: Microsoft 365 Business サブスクリプションで提供されるライセンスでは、Microsoft 365 Business で使用可能な設定に対応する Intune の設定のみを変更できます。 
  
選択するポリシー名をクリックし、左側のナビゲーションで [ **全般]、[割り当て**]、[ **許可されるアプリ**]、[ **適用から除外されるアプリ**]、[ **必須の設定**]、または [ **詳細設定**] を選んで、指定できる設定を調べます。 
  
|**Windows 10 のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|作業ファイルを暗号化する  <br/> |**Advanced settings** \> **Data protection**: **Revoke encryption keys on unenroll** and **Revoke access to protected data device enrolls to MDM** are both set to **On**.  <br/> |
|ユーザーが会社のデータを個人用ファイルにコピーできないようにします。  <br/> |**Required settings** \> **Windows Information Protection mode**. **On** in Microsoft 365 Business maps to: **Hide Overrides**, **Off** in Microsoft 365 Business maps to : **Off**.  <br/> |
|Office ドキュメントのアクセスの制御  <br/> | Microsoft 365 Business でこれが [ **オン**] に設定されている場合  <br/> **Advanced settings** \> **Access**, **Use Windows Hello for Business as a method for signing into Windows** is set to **On**, with the following additional settings:  <br/> **PIN に必要な最小文字数を設定します**: **4**  <br/> **Windows Hello for Business 用の PIN に大文字を使うことを構成します**: **PIN に大文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に小文字を使うことを構成します**: **PIN に小文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に特殊文字を使うことを構成します**: **PIN に特殊文字の使用を許可しない**  <br/> **PIN を変更するようにシステムからユーザーに要求が出されるまでの期間 (日数) を指定します**: **0**  <br/> **再利用できないユーザー アカウントに関連付けることができる以前の PIN の数を指定します**: **0**  <br/> **デバイスがワイプされるまでの認証失敗の回数**: Microsoft 365 Business と同じ (既定値は 5)  <br/> **デバイスが PIN またはパスワードでロックされるまでの最大のアイドル時間 (分)**: Microsoft 365 Business と同じ  <br/> |
|保護されたデータの回復を有効にする  <br/> |**Advanced settings** \> **Data protection**: **Show the enterprise data protection icon** and **Use Azure RMS for WIP** are set to **On**.  <br/> |
|その他の会社のクラウドの場所を保護する  <br/> |**Advanced settings** \> **Protected domains** and **Cloud resources** show domains and SharePoint sites.  <br/> |
|これらのアプリで使用されるファイルを保護する  <br/> |保護されるアプリの一覧が、[ **許可されるアプリ**] に一覧表示されます。  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 デバイスの保護の設定

次の表では、Windows 10 デバイスの構成の設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を検索するには、Microsoft 365 Business 管理者の資格情報を使用してサインインしている間に、 [Azure portal](https://portal.azure.com)に移動し、[**その他のサービス**] を選択して、**フィルター**に intune を入力し、[ **intune** \>デバイス] を選択します。 **構成** \> **プロファイル**。 Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Windows 10 のデバイス ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する  <br/> |リアルタイム監視を許可する: オン  <br/> クラウド保護を許可する: オン  <br/> ユーザーにサンプルの提出を指示する: 安全なサンプルを自動的に送信する (既定では PII は自動送信されません)  <br/> |
|Microsoft Edge で Web ベースの脅威から PC を保護する  <br/> |[ **Microsoft Edge ブラウザーの設定**] の [ **SmartScreen**] が [ **必須**] に設定されます。  <br/> |
|指定の時間アイドル状態が続いた場合にデバイスの画面をオフにする (分)  <br/> |画面がロックされるまでの非アクティブな最長時間 (分)  <br/> |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  <br/> |カスタム URI ポリシー  <br/> |
|ユーザーが Cortana にアクセスすることを許可する  <br/> |**General** \> **Cortana** is set to **block** in Intune when set to **off** in Microsoft 365 Business.  <br/> |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  <br/> |Microsoft 365 Business でこれが [ **オフ**] に設定されている場合、[ **Windows スポットライト**] はすべてブロックされます。  <br/> |
|Windows 10 デバイスを自動的に最新の状態に維持する  <br/> | This setting is in **Microsoft Intune** \> **Service updates - Windows 10 Update Rings**, choose U **pdate policy for Windows 10 devices**, and then **Properties** \> **Settings**.  <br/>  Microsoft 365 Business で [ **オン**] に設定されている場合、以下がすべて設定されます。  <br/> **サービス ブランチ**: **CB** (Microsoft 365 Business でこれがオフの場合は CBB)  <br/> **Microsoft 製品の更新プログラム**: **許可**  <br/> **Windows ドライバー**: **許可**  <br/> **自動更新の動作**: **メンテナンス時に自動的にインストールする**  <br/> **アクティブ時間の開始**: **6 AM**  <br/> **アクティブ時間の終了**: **10 PM**  <br/> **品質更新プログラムの延期期間 (日数)**: **0**  <br/> **機能更新プログラムの延期期間 (日数)**: **0**  <br/> **配信の最適化ダウンロード モード**: **HTTP と同じ NAT でのピアリングの組み合わせ**  <br/> |
|||
   

