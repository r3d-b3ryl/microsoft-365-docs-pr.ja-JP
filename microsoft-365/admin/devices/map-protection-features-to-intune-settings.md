---
title: Intune の設定にマップする方法Microsoft 365 Business Premium保護機能
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 02/27/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: アプリ内の保護機能が Intune Microsoft 365 Business Premiumマップする方法について学習します。 サブスクリプションは、Intune 設定を変更するライセンスを提供します。
ms.openlocfilehash: 33dfb7b53e048f258c1974ced046deaad41f5ce2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313763"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Intune の設定にマップする方法Microsoft 365 Business Premium保護機能

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

## <a name="android-and-ios-application-protection-settings"></a>Android および iOS アプリケーションの保護の設定

次の表では、Android および iOS アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
Intune の設定を確認するには、管理者資格情報を使用してサインインMicrosoft 365 Business Premium管理センター、Intune に移動 **します**。
  
 > [!IMPORTANT]
 > 
 > サブスクリプションMicrosoft 365 Business Premium Intune のすべての設定を変更するライセンスが提供されます。 「 [はじめに Intune の概要」を参照してください。](/intune/introduction-intune)
  
たとえば、Android 用アプリケーション ポリシーなど、&mdash;&mdash;必要なポリシー名を選択し、[ポリシー設定] **を選択します**。
  
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
|作業ファイルを暗号化する  <br/> |アプリケーション データを暗号化する  <br/> |
|[ **ユーザーによるモバイル デバイスの Office ファイルのアクセス方法を管理する**] の設定 <br/> ||
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> | アクセスのために PIN を要求する  <br/>  これにより、以下も設定されます。  <br/> **単純な PIN を許可する**: **はい** <br/> **PIN の長さ**: 4  <br/> **PIN の代わりに指紋認証を許可する**: **はい** <br/> **デバイス PIN が管理されている場合にアプリ PIN を無効にする**: **いいえ** <br/> |
|ログインが何度も失敗した場合に PIN をリセットする (PIN が必要ない場合は無効)  <br/> |[暗証番号をリセットするまでの試行数]  <br/> |
|アプリのアイドル状態がOfficeユーザーにもう一度サインインを要求する (PIN が必要ない場合は無効)  <br/> | (分数) 後にアクセス要件を再確認する  <br/>  これにより、以下も設定されます。  <br/> **タイムアウト**: 分数  <br/>  これは、Microsoft 365 Business で設定したものと同じ分数です。  <br/> **オフラインの猶予期間**: 720 分 (既定値)  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |脱獄されたデバイスまたは root 化されたデバイスで管理対象アプリが実行されることを禁止する  <br/> |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  <br/> | 他のアプリとの間で切り取り、コピー、貼り付けを制限する  <br/>  [アプリ] Microsoft 365 Business Premiumが **[オン**] に設定されている場合、次の 3 つのオプションも Intune のすべての **アプリに** 設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする** <br/> **このアプリで他のアプリからデータを受信できるようにする** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する** <br/>  Microsoft 365 Business のオプションが [ **オン**] に設定されている場合、Intune の以下のすべてのオプションが次のように設定されます。  <br/> **このアプリから他のアプリにデータを転送できるようにする**: **ポリシーで管理されているアプリ** <br/> **このアプリで他のアプリからデータを受信できるようにする**: **すべてのアプリ** <br/> **他のアプリとの間で切り取り、コピー、貼り付けを制限する**: **貼り付けを使用する、ポリシーで管理されているアプリ** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 アプリの保護の設定

次の表では、Windows 10 アプリケーションのポリシーの設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を見つけるには、管理者資格情報を使用Microsoft 365 Business Premiumサインインし、[Azure portal に移動します](https://portal.azure.com)。 [その **他のサービス]** を選択し、[フィルター] に「Intune」と **入力します**。 **[Intune アプリ保護アプリ ポリシー]** \> **を選択します**。
  
 > [!IMPORTANT]
 >
 >サブスクリプションMicrosoft 365 Business Premiumは、Intune の設定のみを変更するライセンスを提供し、このサブスクリプションで使用できる設定にマップMicrosoft 365 Business Premium。 
  
使用可能な設定を確認するには、必要なポリシー名を選択し、左側のナビゲーション ウィンドウから [全般]、[割り当て]、[許可されたアプリ]、[アプリの除外]、[必須の設定]、または [詳細設定] を選択します。  
  
|**Windows 10 のアプリケーション ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|作業ファイルを暗号化する  <br/> |**Advanced settings** \> **Data protection**: **Revoke encryption keys on unenroll** and **Revoke access to protected data device enrolls to MDM** are both set to **On**.  <br/> |
|ユーザーが会社のデータを個人ファイルにコピーするのを防ぐ。  <br/> |**Required settings** \> **Windows Information Protection mode**. **On** in in Microsoft 365 Business Premium マップ: **非表示 オーバーライド**, **Off in Microsoft 365 Business Premium** マップ: **Off**.  <br/> |
|Office ドキュメントのアクセスの制御  <br/> | この設定が [**オン] に** 設定されている場合Microsoft 365 Business Premium  <br/> **Advanced settings** \> **Access**, **Use Windows Hello for Business as a method for signing into Windows** is set to **On**, with the following additional settings:  <br/> **PIN に必要な最小文字数を設定します**: **4**  <br/> **Windows Hello for Business 用の PIN に大文字を使うことを構成します**: **PIN に大文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に小文字を使うことを構成します**: **PIN に小文字の使用を許可しない**  <br/> **Windows Hello for Business 用の PIN に特殊文字を使うことを構成します**: **PIN に特殊文字の使用を許可しない**  <br/> **システムがユーザーに変更を要求** する前に PIN を使用できる期間 (日数) を **0 に設定します**。  <br/> **再利用できないユーザー アカウントに関連付けることができる以前の PIN の数を指定します**: **0**  <br/> **デバイスがワイプされるまでの認証失敗の回数**: Microsoft 365 Business と同じ (既定値は 5)  <br/> **デバイスが PIN またはパスワードでロックされるまでの最大のアイドル時間 (分)**: Microsoft 365 Business と同じ  <br/> |
|保護されたデータの回復を有効にする  <br/> |**Advanced settings** \> **Data protection**: **Show the enterprise data protection icon** and **Use Azure RMS for WIP** are set to **On**.  <br/> |
|その他の会社のクラウドの場所を保護する  <br/> |**Advanced settings** \> **Protected domains** and **Cloud resources** show domains and SharePoint sites.  <br/> |
|これらのアプリで使用されるファイルを保護する  <br/> |保護されるアプリの一覧が、[ **許可されるアプリ**] に一覧表示されます。  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 デバイスの保護の設定

次の表では、Windows 10 デバイスの構成の設定と Intune の設定の対応について詳しく説明します。
  
Intune 設定を見つけるには、Microsoft 365 Business Premium 管理者資格情報でサインインし、[Azure portal](https://portal.azure.com) に移動し、[その他のサービス] を選択し、[フィルター] に Intune と入力し、[**Intune** \> **デバイス**\>構成プロファイル] を選択します。 Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Windows 10 のデバイス ポリシーの設定**|**Intune の設定**|
|:-----|:-----|
|Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する  <br/> |リアルタイム監視を許可する: オン  <br/> クラウド保護を許可する: オン  <br/> ユーザーにサンプルの提出を指示する: 安全なサンプルを自動的に送信する (既定では PII は自動送信されません)  <br/> |
|Microsoft Edge で Web ベースの脅威から PC を保護する  <br/> |[ **Microsoft Edge ブラウザーの設定**] の [ **SmartScreen**] が [ **必須**] に設定されます。  <br/> |
|指定の時間アイドル状態が続いた場合にデバイスの画面をオフにする (分)  <br/> |画面がロックされるまでの非アクティブな最長時間 (分)  <br/> |
|ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する  <br/> |カスタム URI ポリシー  <br/> |
|ユーザーが Cortana にアクセスすることを許可する  <br/> |**全般** \>**Cortana** でオフに **設定すると**、Intune でブロックMicrosoft 365 Business Premium。  <br/> |
|ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する  <br/> |**Windowsスポット** ライトで、この設定が [オフ] に設定されている場合は、すべて **ブロックMicrosoft 365 Business Premium。**  <br/> |
|Windows 10 デバイスを自動的に最新の状態に維持する  <br/> | この設定は、[サービス\>Microsoft Intune **- Windows 10**\>リング] の順に選択し、[Windows 10 デバイスのポリシーの更新] を選択し、[プロパティ] **設定。**  <br/>  [設定] Microsoft 365 Business Premiumが **[オン**] に設定されている場合、次のすべての設定が設定されます。  <br/> **サービス ブランチは** CB に設定 **されます** (この機能が無効になっている場合は CBB Microsoft 365 Business Premium)。  <br/> **Microsoft 製品の更新プログラム**: **許可**  <br/> **Windows ドライバー**: **許可**  <br/> **自動更新の動作**: **メンテナンス時に自動的にインストールする**  <br/> **アクティブ時間の開始**: **6 AM**  <br/> **アクティブ時間の終了**: **10 PM**  <br/> **品質更新プログラムの延期期間 (日数)**: **0**  <br/> **機能更新プログラムの延期期間 (日数)**: **0**  <br/> **配信の最適化ダウンロード モード**: **HTTP と同じ NAT でのピアリングの組み合わせ**  <br/> |
|||

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../security-and-compliance/secure-your-business-data.md)