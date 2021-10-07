---
title: クラウド保護と Microsoft Defender ウイルス対策
description: クラウド保護とクラウド のMicrosoft Defender ウイルス対策
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、次世代 AV、機械学習、マルウェア対策、セキュリティ、防御、クラウド、クラウド保護
search.product: eADQiWindows 10XVcnh
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
ms.date: 09/22/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 82f40a1110a93a44fe8b1712568d15bd849bd975
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169865"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>クラウド保護と Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

新しい脅威や新Microsoft Defender ウイルス対策に対する、ほぼ即座に自動化された保護を提供する次世代テクノロジ。 新しい脅威を動的に特定するために、次世代テクノロジは、Microsoft Intelligent Security Graph および高度な機械学習モデルによって駆動される強力な人工知能 (AI) システムで、多数の相互接続されたデータを処理します。 クラウド保護は、正確でMicrosoft Defender ウイルス対策インテリジェントな保護を提供するために、クラウド保護と共に機能します。 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="クラウド保護とクラウド保護の機能を示す図Microsoft Defender ウイルス対策":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> クラウド保護を有効に保つことをお勧めします。 詳細については、「クラウド保護を[有効にする理由」](why-cloud-protection-should-be-on-mdav.md)を参照Microsoft Defender ウイルス対策。 

## <a name="how-cloud-protection-works"></a>クラウド保護のしくみ

Microsoft Defender ウイルス対策 Microsoft クラウド サービスとシームレスに連携します。 Microsoft Advanced Protection Service (MAPS) とも呼ばれるこれらのクラウド保護サービスは、標準のリアルタイム保護を強化します。 クラウド保護により、次世代テクノロジは、単一のエンドポイントが感染する前でも、新しい脅威を迅速に特定できます。 

次のブログ投稿は、クラウド保護のしくみを示しています。

- [Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジを知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [エンタープライズMicrosoft Defender ウイルス対策最も多く展開されている理由](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [機械学習と組み合わせた動作監視は、大規模なコイン マイニング キャンペーンを台無しにする](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [人工知能が "Emotet" の発生を停止した方法](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [悪いうさぎの削除: Microsoft Defender ウイルス対策機械学習の防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Microsoft Defender ウイルス対策クラウド保護サービス: 前に見たことの無いマルウェアに対する高度なリアルタイム防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> クラウド Microsoft Defender ウイルス対策は、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスは、単にクラウドに保存されているファイルを保護する機能ではありません。代わりに、クラウド サービスは分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

## <a name="how-to-get-cloud-protection"></a>クラウド保護を取得する方法 

クラウド保護は既定で有効になっています。 ただし、以前の組織ポリシーの一部として無効になっている場合は、再び有効にする必要があります。 詳細については、「クラウド保護を [有効にする」を参照してください](enable-cloud-protection-microsoft-defender-antivirus.md)。

サブスクリプションに E5 Windows 10含まれる場合は、緊急の動的インテリジェンス更新プログラムを利用できます。これは、新たな脅威からほぼリアルタイムで保護されます。 クラウド保護を有効にした場合、マルウェアの問題に対する修正プログラムは、次の更新を待つのではなく、数分以内にクラウド経由で配信できます。 「クラウド サービスMicrosoft Defender ウイルス対策レポートに基づいて新しい保護更新プログラムを自動的に受信する[方法の構成」を参照してください](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)。

## <a name="next-steps"></a>次の手順

クラウド保護の概要を次に示Microsoft Defender ウイルス対策次の手順を示します。

1. 「[クラウド保護を有効にする理由」を参照Microsoft Defender ウイルス対策。](why-cloud-protection-should-be-on-mdav.md)

2. [クラウド保護を [有効にする] に進む](enable-cloud-protection-microsoft-defender-antivirus.md)