---
title: クラウドによる保護と Microsoft Defender ウイルス対策
description: クラウド配信の保護と Microsoft Defender ウイルス対策の詳細
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、次世代 av、機械学習、マルウェア対策、セキュリティ、防御、クラウド、クラウド配信の保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: e967cb9efe03fc180bda531f192f3143c311796d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764761"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>クラウドによる保護を通じて Microsoft Defender ウイルス対策で次世代テクノロジを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

Microsoft Defender Antivirus の Microsoft 次世代テクノロジは、新しい脅威や新たな脅威に対するほぼ瞬時の自動保護を提供します。 新しい脅威を動的に識別するために、これらのテクノロジは、Microsoft インテリジェント セキュリティ グラフの相互接続された大量のデータおよび高度な機械学習モデルによって駆動される強力な人工知能 (AI) システムと連携します。  

Microsoft Defender Antivirus は、複数の検出および防止テクノロジを使用して、正確でリアルタイムでインテリジェントな保護を提供します。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ[を知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV エンジンの一覧](images/microsoft-defender-atp-next-generation-protection-engines.png)  

これらの次世代テクノロジのパワーとスピードを活用するために、Microsoft Defender Antivirus は Microsoft クラウド サービスとシームレスに連携します。 Microsoft Advanced Protection Service (MAPS) とも呼ばれるこれらのクラウド保護サービスは、標準のリアルタイム保護を強化し、間違いなく最高のウイルス対策防御を提供します。 

>[!NOTE]
>Microsoft Defender ウイルス対策クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスと呼ばれるのは、単にクラウドに保存されたファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

クラウドによる保護により、次世代テクノロジは、単一のコンピューターが感染する前でも、新しい脅威を迅速に特定できます。 Microsoft AI と Microsoft Defender ウイルス対策の動作に関する次のビデオをご覧ください。 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

次世代テクノロジがクラウドを通じて保護配信時間を短縮する方法を理解するには、次のビデオをご覧ください。 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

クラウド保護と Microsoft AI に関する詳細な保護ストーリーについては、次のブログ記事を参照してください。 

- [Microsoft Defender ウイルス対策が企業で最も展開されている理由](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [機械学習と組み合わせた動作監視は、大規模な Dofoil コイン マイニング キャンペーンを台無しにする](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [人工知能がエモテットの流行を止めた方法](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [悪いうさぎを削除する: Microsoft Defender Antivirus とレイヤード 機械学習の防御](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender ウイルス対策クラウド保護サービス: 前に見たことの無いマルウェアに対する高度なリアルタイム防御](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>クラウドによる保護を取得する 

クラウド配信の保護は既定で有効になっています。 ただし、以前の組織ポリシーの一部として無効になっている場合は、再び有効にする必要があります。

Windows 10 E5 を実行している組織は、緊急の動的インテリジェンス更新プログラムを利用して、新たな脅威からほぼリアルタイムで保護できます。 クラウドによる保護を有効にした場合、マルウェアの問題に対する修正プログラムは、次の更新を待たずに、数分以内にクラウド経由で配信できます。

>[!TIP]
>また、テストグラウンドのWindows Defenderにアクセスして demo.wd.microsoft.com 機能[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)が動作しているのを確認し、その動作を確認できます。

次の表に、最新バージョンの Windows と Configuration Manager の間のクラウドによる保護の違いについて説明します。

|OS バージョンまたはサービス アプリケーション |クラウド保護サービス ラベル  |レポート レベル (MAPS メンバーシップ レベル)  |クラウド ブロックのタイムアウト期間  |
|---------|---------|---------|---------|
|Windows 8.1 (グループ ポリシー)     |Microsoft Advanced Protection Service   |基本、高度   |いいえ         |
|Windows 10 バージョン 1607 (グループ ポリシー)  |Microsoft Advanced Protection Service      |詳細情報         |いいえ         |
|Windows 10 バージョン 1703 以上 (グループ ポリシー)      |クラウドベースの保護      |詳細情報         |構成可能         |
|System Center 2012 Configuration Manager  |      該当なし         |Windows のバージョンに依存         |構成不可 |
|Microsoft Endpoint Manager (Current Branch)         |クラウド保護サービス         |Windows のバージョンに依存          |構成可能         |
|Microsoft Intune     |Microsoft Advanced Protection Service         |Windows のバージョンに依存         |構成可能         |

Microsoft Defender ウイルス [対策を構成して、クラウド](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)サービスからのレポートに基づいて新しい保護更新プログラムを自動的に受信することもできます。


## <a name="tasks"></a>タスク

- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)。 Microsoft Endpoint Configuration Manager、グループ ポリシー、Microsoft Intune、および PowerShell コマンドレットを使用して、クラウドによる保護を有効にできます。

- [クラウド配信の保護レベルを指定します](specify-cloud-protection-level-microsoft-defender-antivirus.md)。 グループ ポリシーと Microsoft Endpoint Configuration Manager を使用して、クラウドによって提供される保護のレベルを指定できます。 保護レベルは、クラウドと共有される情報の量と、新しいファイルのブロックを積極的に行う方法に影響します。

- [Microsoft Defender ウイルス対策のネットワーク接続を構成および検証します](configure-network-connections-microsoft-defender-antivirus.md)。 クラウド配信の保護を効果的に機能するには、ネットワークとエンドポイントが接続できる必要がある Microsoft の URL があります。 この記事では、ファイアウォールまたはネットワーク フィルタールールを介して許可する URL と、ネットワークがクラウド配信保護に適切に登録されていることを確認する手順を示します。

- [ブロックを一目で構成する機能](configure-block-at-first-sight-microsoft-defender-antivirus.md)。 "一目でブロック" 機能を使用すると、従来のセキュリティ インテリジェンスを数時間待つことなく、数秒で新しいマルウェアをブロックできます。 Microsoft Endpoint Manager とグループ ポリシーを使用して有効にして構成できます。

- [クラウド ブロックのタイムアウト期間を構成します](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 Microsoft Defender ウイルス対策は、クラウド配信の保護サービスに対するクエリ中に、疑わしいファイルの実行をブロックできます。 Microsoft Endpoint Manager とグループ ポリシーを使用してファイルの実行を妨げる時間を構成できます。