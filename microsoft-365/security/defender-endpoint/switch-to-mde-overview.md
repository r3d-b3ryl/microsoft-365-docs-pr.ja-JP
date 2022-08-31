---
title: Microsoft 以外のエンドポイント保護からMicrosoft Defender for Endpointへの切り替えを行う
description: エンドポイント保護ソリューションの Microsoft Defender ウイルス対策を含むMicrosoft Defender for Endpointに切り替えます。
keywords: 移行, Windows Defender, 高度なエンドポイント保護, ウイルス対策, マルウェア対策, パッシブ モード, アクティブ モード
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365initiative-defender-endpoint
- highpri
ms.topic: overview
ms.custom: migrationguides
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 5194200b942870f27f784b11c55cd8dbba2e816f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470687"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft 以外のエンドポイント保護からMicrosoft Defender for Endpointへの切り替えを行う

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Microsoft 以外のエンドポイント保護ソリューションから [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) への切り替えを検討している場合、または計画段階にある場合は、この記事をガイドとして使用してください。 この記事では、Defender for Endpoint に移行する全体的なプロセスについて説明します。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="エンドポイント保護ソリューションを Defender for Endpoint に切り替える移行プロセス" lightbox="images/nonms-mde-migration.png":::

Defender for Endpoint に切り替えると、Microsoft 以外のウイルス対策/マルウェア対策保護がアクティブ モードで開始されます。 次に、パッシブ モードで Microsoft Defender ウイルス対策を構成し、デバイスを Defender for Endpoint にオンボードします。 次に、エンドポイント保護機能を構成し、Microsoft Defender ウイルス対策をアクティブ モードに設定し、すべてが正しく動作していることを確認します。 最後に、Microsoft 以外のソリューションを削除します。

## <a name="the-migration-process"></a>移行プロセス

Defender for Endpoint に移行するプロセスは、次の表に示すように、3 つのフェーズに分けることができます。

:::image type="content" source="images/phase-diagrams/migration-phases.png" alt-text="MDE 移行プロセス" lightbox="images/phase-diagrams/migration-phases.png":::


<br/><br/>

|段階|説明|
|--|--|
|[移行の準備](switch-to-mde-phase-1.md)|[**準備** フェーズ中](switch-to-mde-phase-1.md): <br/>1. 組織のデバイスを更新します。<br/>2. Defender for Endpoint を取得します。<br/>3. ロールとアクセス許可を計画し、Microsoft 365 Defender ポータルへのアクセスを許可します。<br/>4. 組織のデバイスと Defender for Endpoint 間の通信を有効にするために、デバイス プロキシとインターネット設定を構成します。 |
|[Defender for Endpoint を設定する](switch-to-mde-phase-2.md)|[**セットアップ** フェーズ中:](switch-to-mde-phase-2.md) <br/>1. Microsoft Defender ウイルス対策を有効/再インストールし、パッシブ モードに設定します。<br/>2. Defender for Endpoint を構成します。<br/>3. 既存のソリューションの除外リストに Defender for Endpoint を追加します。<br/>4. Microsoft Defender ウイルス対策の除外リストに既存のソリューションを追加します。<br/>5. デバイス グループ、コレクション、および組織単位を設定します。<br/>6. マルウェア対策ポリシーとリアルタイム保護設定を構成します。|
|[Defender for Endpoint へのオンボード](switch-to-mde-phase-3.md)|[**オンボード** フェーズ中](switch-to-mde-phase-3.md): <br/>1. デバイスを Defender for Endpoint にオンボードします。<br/>2. 検出テストを実行します。<br/>3. Microsoft Defender ウイルス対策がパッシブ モードで実行されていることを確認します。<br/>4. Microsoft Defender ウイルス対策の更新プログラムを取得します。<br/>5. 既存のエンドポイント保護ソリューションをアンインストールします。<br/>6. Defender for Endpoint が正しく動作していることを確認します。|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointには何が含まれていますか?

この移行ガイドでは、Defender for Endpoint に移行するための開始点として、[次世代の保護](microsoft-defender-antivirus-in-windows-10.md)[とエンドポイントの検出と応答](overview-endpoint-detection-response.md)機能に重点を置いています。 ただし、Defender for Endpoint には、ウイルス対策とエンドポイント保護以上のものが含まれています。 Defender for Endpoint は、予防保護、違反後の検出、自動調査、および対応のための統合プラットフォームです。 次の表は、Defender for Endpoint の機能と機能をまとめたものです。

<br/><br/>

|機能/機能|説明|
|---|---|
|[Microsoft Defender 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)|Defender の脆弱性管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。|
|[攻撃面の減少](overview-attack-surface-reduction.md)|攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。|
|[次世代の保護](microsoft-defender-antivirus-in-windows-10.md)|次世代の保護には、脅威やマルウェアをブロックするのに役立つ Microsoft Defender ウイルス対策が含まれています。|
|[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)|エンドポイントの検出機能と応答機能は、侵入の試行とアクティブな侵害を検出、調査、および対応します。|
|[高度な追求](advanced-hunting-overview.md)|高度なハンティング機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを見つけることができます。|
|[動作ブロックと封じ込め](behavioral-blocking-containment.md)|動作ブロック機能とコンテインメント機能は、脅威が実行を開始した場合でも、その動作とプロセス ツリーに基づいて、脅威を特定して停止するのに役立ちます。|
|[調査と修復の自動化](automated-investigations.md)|自動調査と対応機能は、アラートを調べ、直ちに修復アクションを実行して侵害を解決します。|
|[脅威ハンティング サービス](microsoft-threat-experts.md) (Microsoft 脅威エキスパート)|脅威ハンティング サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重大な脅威が見逃されないように支援します。|

**詳細については、こちらを参照してください。 [「Defender for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>次のステップ

- [移行の準備](switch-to-mde-phase-1.md)に進みます。
