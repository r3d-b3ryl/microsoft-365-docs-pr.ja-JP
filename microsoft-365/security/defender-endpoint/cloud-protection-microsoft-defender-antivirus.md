---
title: クラウド保護と Microsoft Defender ウイルス対策
description: クラウドの保護とMicrosoft Defender ウイルス対策について学習する
keywords: Microsoft Defender ウイルス対策, 次世代テクノロジ, 次世代 AV, 機械学習, マルウェア対策, セキュリティ, Defender, クラウド, クラウド保護
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 0cba725ed27d652366e681adccdec8dbefa68ecd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788086"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>クラウド保護と Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策の次世代テクノロジは、新しい脅威や新しい脅威に対してほぼ瞬時に自動化された保護を提供します。 新しい脅威を動的に特定するために、次世代テクノロジは、Microsoft Intelligent Security Graphと高度な機械学習モデルによって駆動される強力な人工知能 (AI) システムで、相互接続された大量のデータと連携します。 クラウド保護は、Microsoft Defender ウイルス対策と連携して、正確でリアルタイムでインテリジェントな保護を実現します。 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="クラウド保護とMicrosoft Defender ウイルス対策の連携方法を示す図" lightbox="images/mde-cloud-protection.png":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> クラウド保護を有効にしておくことをお勧めします。 詳細については、「[Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由」を](why-cloud-protection-should-be-on-mdav.md)参照してください。 

## <a name="how-cloud-protection-works"></a>クラウド保護のしくみ

Microsoft Defender ウイルス対策は、Microsoft クラウド サービスとシームレスに連携します。 これらのクラウド保護サービスは、Microsoft Advanced Protection Service (MAPS) とも呼ばれ、標準のリアルタイム保護を強化します。 クラウド保護を使用すると、次世代テクノロジにより、単一のエンドポイントが感染する前であっても、新しい脅威を迅速に識別できます。 

次のブログ記事は、クラウド保護のしくみを示しています。

- [次世代保護の中核となる高度なテクノロジMicrosoft Defender for Endpoint理解する](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [Microsoft Defender ウイルス対策が企業で最もデプロイされている理由](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [機械学習と組み合わされた行動監視により、大規模なコイン マイニング キャンペーンが台無しになる](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [人工知能によって "Emotet" の発生がどのように停止したか](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [悪いうさぎの起爆: Microsoft Defender ウイルス対策と階層化された機械学習の防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Microsoft Defender ウイルス対策 クラウド保護サービス: 見たことがないマルウェアに対する高度なリアルタイム防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスとして、単にクラウドに格納されているファイルの保護ではありません。代わりに、クラウド サービスは分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新よりもはるかに高速な速度でエンドポイントに保護を提供します。

## <a name="how-to-get-cloud-protection"></a>クラウド保護を取得する方法 

クラウド保護は既定で有効になっています。 ただし、以前の組織ポリシーの一部として無効になっている場合は、再度有効にする必要がある場合があります。 詳細については、「 [クラウド保護を有効にする」](enable-cloud-protection-microsoft-defender-antivirus.md)を参照してください。

サブスクリプションに Windows 10 E5 が含まれている場合は、緊急の動的インテリジェンス更新プログラムを利用できます。これにより、新たな脅威からほぼリアルタイムで保護できます。 クラウド保護を有効にすると、マルウェアの問題に対する修正プログラムは、次の更新プログラムを待つのではなく、数分以内にクラウド経由で配信できます。 [クラウド サービスからのレポートに基づいて新しい保護更新プログラムを自動的に受信するようにMicrosoft Defender ウイルス対策を構成する方法に関するページを参照してください](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

## <a name="next-steps"></a>次の手順

Microsoft Defender ウイルス対策でクラウド保護の概要を確認したので、次のいくつかの手順を次に示します。

1. [Microsoft Defender ウイルス対策に対してクラウド保護を有効にする必要がある理由に関する説明を](why-cloud-protection-should-be-on-mdav.md)参照してください。

2. [クラウド保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)に進む

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)