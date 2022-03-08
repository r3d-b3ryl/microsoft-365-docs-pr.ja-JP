---
title: セキュリティに関する推奨事項がユーザーに与える影響
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Microsoft 365 Business Premium のセキュリティ推奨事項がユーザーに与える影響とデータの保護について説明します。
ms.openlocfilehash: 5704e4c6b0675e8d69ffb2a81b8b6d7bf57bb0b4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331043"
---
# <a name="how-security-recommendations-affect-your-users"></a>セキュリティに関する推奨事項がユーザーに与える影響

このソリューションの Microsoft 365 のセキュリティに関する推奨事項により、ハッカーが環境にアクセスするのがはるかに困難になります。 トレードオフは、ユーザーが、このより安全な環境で作業する方法を認識する必要があるという点です。 少し余分な忍耐が必要な場合は理解していますが、組織を保護する価値があります。

:::image type="content" source="media/m365-democracy-users.png" alt-text="デバイスの重要なポイントを要約した図。":::

## <a name="use-secure-email-practices"></a>セキュリティで保護された電子メールのプラクティスを使用する

すべてのユーザーは、電子メールを安全に保つために、次の電子メールプラクティスを認識して使用する必要があります。

- 認証アプリで多要素認証を使用するメールを設定します。
- 正規のメールを確認し、365 Protection 用 Defender の高度なフィッシングOffice探します。
- 安全なリンクと安全な添付ファイルによって確認された安全なリンクと添付ファイルのみを開きます。

多要素認証 [とフィッシングなどの](m365bp-multifactor-authentication.md) 攻撃 [について詳しくは、次のページをご覧ください](m365-campaigns-phishing-and-attacks.md)。

自分と [チームの](m365-campaigns-protect-campaign-infographic.md) メンバーのためのヒントを含むインフォグラフィックをダウンロードします。

## <a name="set-up-iphones-and-android-devices"></a>iPhone と Android デバイスのセットアップ

環境に追加するユーザーはすべて、 [iPhone と Android](../business/set-up-mobile-devices.md?toc=%2Fmicrosoft-365%2Fcampaigns%2Ftoc.json) デバイスをセットアップして安全に動作するために数分かかる必要があります。

- 認証アプリで多要素認証を使用するデバイスを設定します。
- アプリ ストアから Outlook Mobile、Word、OneDrive、その他の Microsoft アプリを含む Microsoft モバイル アプリを使用します。 iPhone および Android デバイスに含まれるネイティブ メール アプリはサポートされていません。 
- ユーザーがデバイスのロックを解除するには、PIN が必要です。

これらの設定が完了すると、メールを含むこれらのデバイス上の組織データにアクセスするときに、認証アプリの使用を求めるメッセージがユーザーに表示されます。

## <a name="keep-byod-macs-and-windows-10-pcs-fresh"></a>BYOD Mac と Windows 10 PC を最新の状態に保つ

また、ユーザーが主な作業デバイスを最新の状態に保つ必要があります。

- デスクトップ アプリの最新バージョンをインストールOffice、プロンプトが表示されたら、更新プログラムを最新の状態に保つ必要があります。
- Windows の更新プログラムなど、オペレーティング システムの更新プログラムの上に残る。

管理 [されていない Windows 10 および Mac](m365bp-protect-pcs-macs.md) デバイスの場合、ユーザーは基本的なセキュリティ機能が有効になっているか確認する責任があります。

**BYOD Windows 10 および Mac デバイスで基本的なセキュリティ機能を有効にする**

|**Windows 10**|**Mac**|
|:-----|:------|
|BitLocker デバイス保護を有効にする<p><p> [Windows Defenderを維持する] <p>Windows ファイアウォールを有効にする| FileVault を使用して Mac ディスクを暗号化する <p><p>信頼性の高いウイルス対策ソフトウェアを使用する <p>ファイアウォール保護を有効にする|

これらの推奨事項の詳細については、「アカウントとデバイスをハッカーやマルウェアから保護 [する」を参照してください](https://support.office.com/article/Protect-your-account-and-devices-from-hackers-and-malware-066d6216-a56b-4f90-9af3-b3a1e9a327d6#ID0EAABAAA=Windows_10)。

## <a name="collaborate-using-microsoft-teams-onedrive-sharepoint-online-and-other-tools"></a>Microsoft Teams、OneDrive、SharePoint Online、その他のツールを使用した共同作業

ユーザーは、組織のファイルを Microsoft 365 以外の場所で共有して保存する場合があります。 Microsoft 365 を使用すると、可能な限り簡単に共同作業を行い、安全に共有できます。 ファイルと [ビデオは](share-files-and-videos.md) 、Microsoft Teams、OneDrive、Stream、およびファイル内から直接共有できます。 これらのツール内からの共有は、データの漏洩を防ごうのに役立ちます。 機密データに追加の保護を追加して、組織外での共有を防止できます。

## <a name="set-up-managed-windows-10-devices"></a>管理 Windows 10 デバイスのセットアップ

最も重要なスタッフ メンバーは、管理する新しく取得した Windows 10 デバイスを使用することをお勧めします。 これらのデバイスを管理およびセキュリティ保護 [する方法を示します](../business/set-up-windows-devices.md?toc=/microsoft-365/campaigns/toc.json)。 これにより、ハッカーにとって最も価値の高いターゲットであるスタッフメンバーが最も多くの保護を受け取る。
