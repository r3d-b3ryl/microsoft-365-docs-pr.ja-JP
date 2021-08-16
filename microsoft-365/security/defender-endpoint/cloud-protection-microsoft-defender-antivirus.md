---
title: クラウド配信保護と Microsoft Defender ウイルス対策
description: クラウドで提供される保護とセキュリティについてMicrosoft Defender ウイルス対策
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、次世代 AV、機械学習、マルウェア対策、セキュリティ、ディフェンダー、クラウド、クラウド配信の保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: a6e4e76f75bc5eebdf17ce4768eb13327abe630d5aff6d66033ffab43d9ad263
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854341"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>クラウド配信保護と Microsoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

新しい脅威や新Microsoft Defender ウイルス対策に対する、ほぼ即座に自動化された保護を提供する次世代テクノロジ。 新しい脅威を動的に特定するために、次世代テクノロジは、Microsoft Intelligent Security Graph および高度な機械学習モデルによって駆動される強力な人工知能 (AI) システムで、多数の相互接続されたデータを処理します。 Microsoft Defender ウイルス対策は、複数の検出および防止テクノロジを使用して、正確でリアルタイムでインテリジェントな保護を提供します。 

> [!TIP]
> 詳細な情報をご希望ですか? ブログの投稿を参照してください。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ [を知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

Microsoft Defender ウイルス対策 Microsoft クラウド サービスとシームレスに連携します。 Microsoft Advanced Protection Service (MAPS) とも呼ばれるこれらのクラウド保護サービスは、標準のリアルタイム保護を強化し、間違いなく最高のウイルス対策防御を提供します。 

> [!NOTE]
> クラウド Microsoft Defender ウイルス対策は、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスは、単にクラウドに保存されているファイルを保護する機能ではありません。代わりに、クラウド サービスは分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

クラウドによる保護により、次世代テクノロジは、単一のコンピューターが感染する前でも、新しい脅威を迅速に特定できます。 次のブログ投稿は、クラウド配信の保護のしくみを示しています。

- [エンタープライズMicrosoft Defender ウイルス対策最も多く展開されている理由](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [機械学習と組み合わせた動作監視は、大規模なコイン マイニング キャンペーンを台無しにする](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工知能が "Emotet" の発生を停止した方法](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [悪いうさぎの削除: Microsoft Defender ウイルス対策機械学習の防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender ウイルス対策クラウド保護サービス: 前に見たことの無いマルウェアに対する高度なリアルタイム防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>クラウド配信の保護を取得する方法 

クラウド配信の保護は既定で有効になっています。 ただし、以前の組織ポリシーの一部として無効になっている場合は、再び有効にする必要があります。 詳細については、「クラウド配信の [保護を有効にする」を参照してください](enable-cloud-protection-microsoft-defender-antivirus.md)。

E5 をWindows 10組織は、緊急の動的インテリジェンス更新を利用して、新たな脅威からほぼリアルタイムで保護できます。 クラウドによる保護を有効にした場合、マルウェアの問題に対する修正プログラムは、次の更新を待たずに、数分以内にクラウド経由で配信できます。 [クラウド Microsoft Defender ウイルス対策レポートに基づいて新しい保護更新プログラム](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)を自動的に受信する構成を構成します。

> [!TIP]
> 機能が動作Windows Defender[確認し](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)demo.wd.microsoft.com テストグラウンド Web サイトにアクセスします。

## <a name="next-steps"></a>次の手順

1. [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)。 クラウドによる保護を有効にするには、Microsoft エンドポイント マネージャー 、グループ ポリシー、または PowerShell コマンドレット (Microsoft Endpoint Configuration ManagerとMicrosoft Intuneが含まれています)。

2. [クラウド配信の保護レベルを指定します](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 クラウドによって提供される保護のレベルを指定するには、クラウド またはグループ Microsoft エンドポイント マネージャーを使用します。 保護レベルは、クラウドと共有される情報の量と、新しいファイルのブロックを積極的に行う方法に影響します。

3. [ネットワーク接続の構成と検証を行Microsoft Defender ウイルス対策。](configure-network-connections-microsoft-defender-antivirus.md) クラウド配信の保護を効果的に機能するには、ネットワークとエンドポイントが接続できる必要がある Microsoft の URL があります。 この記事では、ファイアウォールまたはネットワーク フィルタールールを介して許可する URL と、ネットワークがクラウド配信保護に適切に登録されていることを確認する手順を示します。

4. ["一目でブロックする" 機能を構成します](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 "一目でブロック" 機能を使用すると、従来のセキュリティ インテリジェンスを数時間待つことなく、数秒で新しいマルウェアをブロックできます。 グループ ポリシーまたはグループ ポリシーを使用して、Microsoft エンドポイント マネージャー構成できます。

5. [クラウド ブロックのタイムアウト期間を構成します](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender ウイルス対策提供された保護サービスに対するクエリ中に、疑わしいファイルの実行をブロックできます。 グループ ポリシーまたはグループ ポリシーを使用して、ファイルの実行を妨げる時間Microsoft エンドポイント マネージャー構成できます。