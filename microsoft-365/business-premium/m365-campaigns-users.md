---
title: これらのセキュリティに関する推奨事項がユーザーに与える影響
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
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
description: Microsoft 365 Business Premium に関するこれらのセキュリティの推奨事項がユーザーにどのように影響し、データを保護するかについて説明します。
ms.openlocfilehash: 30e609a6dc74ef8a0303c93f65eb44a4003d3a99
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893141"
---
# <a name="how-these-security-recommendations-affect-your-microsoft-365-users"></a>これらのセキュリティに関する推奨事項が Microsoft 365 ユーザーに与える影響

このソリューションでの Microsoft 365 のセキュリティに関する推奨事項により、ハッカーが環境にアクセスするのがはるかに困難になります。 トレードオフは、ユーザーがこのより安全な環境内で作業する方法を知っている必要があるということです。 少し余分な忍耐が必要であることは理解していますが、組織を保護することは価値があります。

![iPhone、Android デバイス、Mac、Windows 10、共有、および主要なスタッフの重要なポイントを下からまとめた図。](../media/M365-democracy-Users_900px.png)

## <a name="use-secure-email-practices"></a>安全なメール設定を使用する

すべてのユーザーは、次のメール設定を認識して使用し、メールを安全に保つのに役立てる必要があります。

- 認証アプリで多要素認証を使用するようにメールを設定します。

- 正当なメールを確認し、高度なフィッシング保護 (Defender for Office 365) からの安全上のヒントを探します。

- 安全なリンクと安全な添付ファイルによって確認されたように、安全なリンクと添付ファイルのみを開きます。

[多要素認証](m365bp-multifactor-authentication.md)、および[フィッシングとその他の攻撃](m365bp-avoid-phishing-and-attacks.md)の詳細をご覧ください。

自分とチームのメンバーのためのヒントを含む[インフォグラフィック](m365-campaigns-protect-campaign-infographic.md)をダウンロードします。

## <a name="set-up-iphones-and-android-devices"></a>iPhone および Android デバイスを設定する

環境に追加するすべてのユーザーは、[iPhone および Android デバイスが安全に動作するようにセットアップする](../business/set-up-mobile-devices.md)のに数分必要とします。

- 認証アプリで多要素認証を使用するようにデバイスを設定します。

- Outlook Mobile、Word、OneDrive、およびアプリ ストアの他の Microsoft アプリを含む、Microsoft モバイル アプリを使用します。 iPhone および Android デバイスに含まれているネイティブ メール アプリはサポートされていません。 

- ユーザーがデバイスのロックを解除するには、PIN が必要です。

これらを設定すると、ユーザーは、これらのデバイス上の組織データ (メールなど) にアクセスするときに、認証アプリを使用するように求められます。

## <a name="keep-byod-macs-and-windows-10-pcs-fresh"></a>BYOD Mac と Windows 10 PC を最新の状態に保つ

また、ユーザーがプライマリ作業デバイスを最新の状態に保つことも重要です。

- 最新バージョンの Office デスクトップ アプリをインストールし、プロンプトが表示されたら、これらを更新して最新の状態に保ちます。

- Windows Update などのオペレーティング システムの更新を常に把握してください。

[管理されていない Windows 10 および Mac デバイス](m365bp-protect-pcs-macs.md)の場合、ユーザーは基本的なセキュリティ機能が有効になっていることを確認する責任があります。

**BYOD Windows 10 および Mac デバイスで基本的なセキュリティ機能を有効にする**

|**Windows 10**|**Mac**|
|:-----|:------|
|BitLocker のデバイス保護を有効にします。<p><p> Windows Defender がオンのままであることを確認する <p>Windows ファイアウォールを有効にする| FileVault を使用して Mac ディスクを暗号化する <p><p>信頼性の高いウイルス対策ソフトウェアを使用する <p>ファイアウォールの保護を有効にする|

これらの推奨事項の詳細については、「[アカウントとデバイスをハッカーやマルウェアから保護する](https://support.office.com/article/Protect-your-account-and-devices-from-hackers-and-malware-066d6216-a56b-4f90-9af3-b3a1e9a327d6#ID0EAABAAA=Windows_10)」を参照してください。

## <a name="collaborate-using-microsoft-teams-onedrive-sharepoint-online-and-other-tools"></a>Microsoft Teams、OneDrive、SharePoint Online、およびその他のツールを使用して共同作業する

ユーザーは、組織のファイルを Microsoft 365 以外の場所で共有および保存したくなる場合があります。 Microsoft 365 を使用すると、共同作業と安全な共有が可能な限り簡単になります。 [ファイルやビデオ](share-files-and-videos.md)は、Microsoft Teams、OneDrive、Stream から直接、さらにはファイル内からでも共有できます。 これらのツール内から共有することで、データの漏洩を防ぐことができます。 機密データに保護を追加して、組織外での共有を防ぐことができます。

## <a name="set-up-managed-windows-10-devices"></a>管理された Windows 10 デバイスを設定する

最も重要なスタッフ メンバーは、管理している新しく取得した Windows 10 デバイスを使用することをお勧めします。 [これらのデバイスを管理および保護する](../business/set-up-windows-devices.md?toc=/microsoft-365/campaigns/toc.json)方法を紹介します。 これにより、ハッカーにとって最も価値の高いターゲットであるスタッフ メンバーが最大限の保護を受けることができます。
