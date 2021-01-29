---
title: これらのセキュリティ推奨事項がユーザーに与える影響
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium に関するこれらのセキュリティ推奨事項がユーザーに与える影響とデータの保護について説明します。
ms.openlocfilehash: 91f6b1fb9ddd5938eb8a788ce7594ec8ab9908c3
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044236"
---
# <a name="how-these-security-recommendations-affect-your-users"></a>これらのセキュリティ推奨事項がユーザーに与える影響

このソリューションの Microsoft 365 のセキュリティに関する推奨事項により、ハッカーが環境にアクセスしにくくなります。 トレードオフは、ユーザーが、このより安全な環境内での作業方法を認識する必要があるという点です。 少しの追加の待ち時間が必要ですが、組織を保護し続ける価値があります。

![iPhone、Android デバイス、Mac、Windows 10、共有、および主要なスタッフに関する以下の重要なポイントを合計した図](../media/M365-democracy-Users_900px.png)

## <a name="use-secure-email-practices"></a>セキュリティで保護された電子メールのプラクティスを使用する

すべてのユーザーは、電子メールのセキュリティを維持するために、次の電子メールプラクティスを認識して使用する必要があります。

- 認証アプリで多要素認証を使用するメールを設定します。
- 正当なメールを確認し、Defender for Office 365 Protection の高度なフィッシングの安全性のヒントを探します。
- 安全なリンクと安全な添付ファイルによって確認された安全なリンクと添付ファイルのみを開きます。

多要素認証 [、フィッシング、](m365-campaigns-multifactor-authenication.md) その [他の攻撃について詳しくは、次をご覧ください](m365-campaigns-phishing-and-attacks.md)。

自分と [チームのメンバー](m365-campaigns-protect-campaign-infographic.md) に関するヒントを含むインフォグラフィックをダウンロードします。

## <a name="set-up-iphones-and-android-devices"></a>iPhone と Android デバイスのセットアップ

環境に追加するユーザーすべてが安全に動作するには [、iPhone](../business/set-up-mobile-devices.md?toc=%2Fmicrosoft-365%2Fcampaigns%2Ftoc.json) と Android デバイスをセットアップするために数分かかる必要があります。

- 認証アプリで多要素認証を使用するデバイスをセットアップします。
- Outlook Mobile、Word、OneDrive、アプリ ストアのその他の Microsoft アプリを含む Microsoft モバイル アプリを使用します。 iPhone と Android デバイスに含まれるネイティブ メール アプリはサポートされていません。 
- ユーザーがデバイスのロックを解除するために PIN を要求します。

これらの設定が完了すると、メールを含むこれらのデバイス上の組織データにアクセスするときに、認証アプリを使用するように求めるメッセージがユーザーに表示されます。

## <a name="keep-byod-macs-and-windows-10-pcs-fresh"></a>BYOD Mac と Windows 10 PC を最新の状態に保つ

また、ユーザーがプライマリ作業デバイスを最新の状態に保つ必要があります。

- 最新バージョンのデスクトップ アプリをインストールOffice、メッセージが表示されたら更新プログラムを使用して最新の状態に保つ必要があります。
- Windows 更新プログラムなど、オペレーティング システムの更新プログラムを最新の情報に残します。

非 [管理対象の Windows 10 デバイスと Mac](m365-campaigns-protect-pcs-macs.md)デバイスの場合、ユーザーは基本的なセキュリティ機能を有効にする責任があります。

**BYOD Windows 10 デバイスと Mac デバイスで基本的なセキュリティ機能を有効にする**

| |**Windows 10**|**Mac**|
|:-----|:-----|:------|
|セキュリティ機能|BitLocker デバイス保護を有効にする<p><p> オンWindows Defender確認する <p>Windows ファイアウォールを有効にする| FileVault を使用して Mac ディスクを暗号化する <p><p>信頼できるウイルス対策ソフトウェアを使用する <p>ファイアウォール保護を有効にする|

これらの推奨事項の詳細については、「アカウントとデバイスをハッカーやマルウェアから保護する [」を参照してください](https://support.office.com/article/Protect-your-account-and-devices-from-hackers-and-malware-066d6216-a56b-4f90-9af3-b3a1e9a327d6#ID0EAABAAA=Windows_10)。

## <a name="collaborate-using-microsoft-teams-onedrive-sharepoint-online-and-other-tools"></a>Microsoft Teams、OneDrive、SharePoint Online、その他のツールを使用して共同作業を行う

ユーザーは、Microsoft 365 以外の場所で組織のファイルを共有して保存する必要がある場合があります。 Microsoft 365 を使用すると、可能な限り簡単に共同作業を行い、安全に共有できます。 ファイルや [ビデオは](share-files-and-videos.md) 、Microsoft Teams、OneDrive、Stream から直接、さらにファイル内からでも共有できます。 これらのツール内からの共有は、データの漏洩を防ごうのに役立ちます。 機密データに保護を追加して、組織外との共有を防止できます。

## <a name="set-up-managed-windows-10-devices"></a>管理対象の Windows 10 デバイスをセットアップする

最も重要なスタッフ メンバーは、管理する新しく取得した Windows 10 デバイスを使用することをお勧めします。 これらのデバイスを管理および保護 [する方法を示します](../business/set-up-windows-devices.md?toc=/microsoft-365/campaigns/toc.json)。 これにより、ハッカーにとって最も価値の高いターゲットであるスタッフ メンバーが最も多くの保護を受け取る必要があります。
