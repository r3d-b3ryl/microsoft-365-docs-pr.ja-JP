---
title: Microsoft 365 Business Premium の保護機能を Intune の設定に対応付ける方法
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
ms.date: 04/21/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Microsoft 365 Business Premium の保護機能を Intune の設定に対応付ける方法について説明します。 サブスクリプションでは、Intune の設定を変更するためのライセンスが提供されます。
ms.openlocfilehash: b5493199b7a2593097d3e4efbf1d4a405fc1ae4b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090635"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Microsoft 365 Business Premium の保護機能を Intune の設定に対応付ける方法

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="android-and-ios-application-protection-settings"></a>Android および iOS アプリケーションの保護の設定

次の表では、Android および iOS アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を見つけるには、Microsoft 365 Business Premium 管理者資格情報でサインインし、**[管理センター]**、**[Intune]** の順に移動します。
  
 > [!IMPORTANT]
 > 
 > Microsoft 365 Business Premium サブスクリプションでは、すべての Intune 設定を変更するためのライセンスが付与されます。 [作業を開始するには「Intune の概要](/intune/introduction-intune)」を参照してください。
  
ポリシーの名前を選択し &mdash;(たとえば、Android のアプリケーション ポリシー)&mdash;、**[ポリシー設定]** を選びます。
  
[ **デバイスの紛失または盗難時の作業ファイルの保護**] の設定
  
|**Android または iOS のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|アクティブでない状態が指定の日数続いたデバイスから作業ファイルを削除する  |アプリのデータがワイプされるまでのオフライン期間 (日数)  |
|OneDrive for Business に作業ファイルを保存するように強制する  <br/> OneDrive for Business だけが許可されることに注意してください  |会社のデータを保存できるストレージ サービスの選択  |
   
[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] の設定
  
|**Android または iOS のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|アクティブでない状態が指定の日数続いたデバイスから作業ファイルを削除する  |アプリのデータがワイプされるまでのオフライン期間 (日数)  |
|OneDrive for Business に作業ファイルを保存するように強制する  <br/> OneDrive for Business だけが許可されることに注意してください  |会社のデータを保存できるストレージ サービスの選択  |
|作業ファイルを暗号化する  |アプリケーション データを暗号化する  |
|[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] の設定 ||
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  | アクセスのために PIN を要求する  <br/>  これにより、以下も設定されます。  <br/> **単純な PIN を許可する**: **はい** <br/> **PIN の長さ**: 4  <br/> **PIN の代わりに指紋認証を許可する**: **はい** <br/> **デバイス PIN が管理されている場合にアプリ PIN を無効にする**: **いいえ** |
|ログインに指定の回数失敗した場合に PIN をリセットする (PIN が必要ない場合は無効)  |[暗証番号をリセットするまでの試行数]  |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある (PIN が必要ない場合は無効)  | (分数) 後にアクセス要件を再確認する  <br/>  これにより、以下も設定されます。  <br/> **タイムアウト**: 分数  <br/>  これは、Microsoft 365 Business で設定したものと同じ分数です。  <br/> **オフラインの猶予期間**: 720 分 (既定値)  |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  |脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する  |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  | 他のアプリとの間で切り取り、コピー、貼り付けを制限する  <br/>  Microsoft 365 Business Premium のオプションが **[ オン]** に設定されている場合、Intune の次の 3 つのオプションも **[すべてのアプリ]** に設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする** <br/> **このアプリで他のアプリからデータを受信できるようにする** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する** <br/>  Microsoft 365 Business のオプションが [ **オン**] に設定されている場合、Intune の以下のすべてのオプションが次のように設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする**: **ポリシーで管理されているアプリ** <br/> **このアプリで他のアプリからデータを受信できるようにする**: **すべてのアプリ** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する**: **貼り付けを使用する、ポリシーで管理されているアプリ** |
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 アプリの保護の設定

次の表では、Windows 10 アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
To find the Intune setting, sign in with your Microsoft 365 Business Premium admin credentials, and go to [Azure portal](https://portal.azure.com). Select **More services**, and type Intune into the **Filter**. Select **Intune App Protection** \> **App Policy**.
  
 > [!IMPORTANT]
 >
 >Microsoft 365 Business Premium サブスクリプションで提供されるライセンスでは、Microsoft 365 Business Premium で使用可能な設定に対応する Intune の設定のみを変更できます。 
  
使用可能な設定を調べるには、ポリシー名を選択し、左側のナビゲーション ウィンドウで **[全般]、[割り当て]**、**[許可されるアプリ]**、**[適用から除外されるアプリ]**、**[必須の設定]**、または **[詳細設定]** を選択します。 
  
|**Windows 10 のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|作業ファイルを暗号化する  |**Advanced settings** \> **Data protection**: **Revoke encryption keys on unenroll** and **Revoke access to protected data device enrolls to MDM** are both set to **On**.  |
|ユーザーが会社のデータを個人用ファイルにコピーできないようにします。  |**Required settings** \> **Windows Information Protection mode**. **On** in Microsoft 365 Business Premium maps to: **Hide Overrides**, **Off** in Microsoft 365 Business Premium maps to: **Off**.  |
|Office ドキュメントのアクセスの制御  | これが Microsoft 365 Business Premium で **[オン]** に設定されている場合は、次の操作を行います。  <br/> **Advanced settings** \> **Access**, **Use Windows Hello for Business as a method for signing into Windows** is set to **On**, with the following additional settings:  <br/> **PIN に必要な最小文字数を設定します**: **4**  <br/> **Windows Hello for Business 用の PIN に大文字を使うことを構成します**: **PIN に大文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に小文字を使うことを構成します**: **PIN に小文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に特殊文字を使うことを構成します**: **PIN に特殊文字の使用を許可しない**  <br/> **PIN を変更するようにシステムからユーザーに要求が出されるまでの期間 (日数) を指定します**: **0**  <br/> **再利用できないユーザー アカウントに関連付けることができる以前の PIN の数を指定します**: **0**  <br/> **デバイスがワイプされるまでの認証失敗の回数**: Microsoft 365 Business と同じ (既定値は 5)  <br/> **デバイスが PIN またはパスワードでロックされるまでの最大のアイドル時間 (分)**: Microsoft 365 Business と同じ  |
|保護されたデータの回復を有効にする  |**Advanced settings** \> **Data protection**: **Show the enterprise data protection icon** and **Use Azure RMS for WIP** are set to **On**.  |
|その他の会社のクラウドの場所を保護する  |**Advanced settings** \> **Protected domains** and **Cloud resources** show domains and SharePoint sites.  |
|これらのアプリで使用されるファイルを保護する  |保護されるアプリの一覧が、[ **許可されるアプリ**] に一覧表示されます。  |
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 デバイスの保護の設定

次の表では、Windows 10 デバイスの構成の設定と Intune の設定の対応について詳しく説明します。
  
To find the Intune setting, sign in with your Microsoft 365 Business Premium admin credentials, and go to [Azure portal](https://portal.azure.com), then select **More services**, and type in Intune into the **Filter**, select **Intune** \> **Device configuration** \> **Profiles**. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Windows 10 のデバイス ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する  |リアルタイム監視を許可する: オン  <br/> クラウド保護を許可する: オン  <br/> ユーザーにサンプルの提出を指示する: 安全なサンプルを自動的に送信する (既定では PII は自動送信されません)  |
|Microsoft Edge で Web ベースの脅威から PC を保護する  |[ **Microsoft Edge ブラウザーの設定**] の [ **SmartScreen**] が [ **必須**] に設定されます。  |
|指定の時間アイドル状態が続いた場合にデバイスの画面をオフにする (分)  |画面がロックされるまでの非アクティブな最長時間 (分)  |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  |カスタム URI ポリシー  |
|ユーザーが Cortana にアクセスすることを許可する  |**General** \> **Cortana** is set to **block** in Intune when set to **off** in Microsoft 365 Business Premium.  |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  |Microsoft 365 Business Premium でこれが **[オフ]** に設定されている場合、**[Windows スポットライト]** はすべてブロックされます。  |
|Windows 10 デバイスを自動的に最新の状態に維持する  | This setting is in **Microsoft Intune** \> **Service updates - Windows 10 Update Rings**, choose **Update policy for Windows 10 devices**, and then **Properties** \> **Settings**.  <br/>  Microsoft 365 Business Premium で **[オン]** に設定されている場合、以下がすべて設定されます。  <br/> **サービス ブランチ** は **CB** (Microsoft 365 Business Premium でこれがオフの場合は CBB) に設定されます。  <br/> **Microsoft 製品の更新プログラム**: **許可**  <br/> **Windows ドライバー**: **許可**  <br/> **自動更新の動作**: **メンテナンス時に自動的にインストールする**  <br/> **アクティブ時間の開始**: **6 AM**  <br/> **アクティブ時間の終了**: **10 PM**  <br/> **品質更新プログラムの延期期間 (日数)**: **0**  <br/> **機能更新プログラムの延期期間 (日数)**: **0**  <br/> **配信の最適化ダウンロード モード**: **HTTP と同じ NAT でのピアリングの組み合わせ**  |

## <a name="see-also"></a>関連項目

[ビジネス プラン用に Microsoft 365 をセキュリティで保護する上位 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)
