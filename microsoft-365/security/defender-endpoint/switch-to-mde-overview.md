---
title: Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え
description: エンドポイント保護ソリューションの機能を含む Microsoft Defender for Endpoint Microsoft Defender ウイルス対策切り替えます。
keywords: 移行、Windows Defender、高度なエンドポイント保護、ウイルス対策、マルウェア対策、パッシブ モード、アクティブ モード
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
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
- m365initiative-defender-endpoint
ms.topic: overview
ms.custom: migrationguides
ms.date: 11/29/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: eb0971c6f5b8fd8bf37f3d33cb65cff8d331e0d0
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62245305"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804) Microsoft 以外のエンドポイント保護ソリューションから[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) への切り替えを検討している場合、または計画段階にある場合は、この記事をガイドとして使用してください。 この記事では、Defender for Endpoint への移行の全体的なプロセスについて説明します。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="エンドポイント保護ソリューションを Defender for Endpoint に切り替えます。":::

Defender for Endpoint に切り替える場合は、アクティブ モードで Microsoft 以外のウイルス対策/マルウェア対策保護から始まります。 次に、パッシブ モードMicrosoft Defender ウイルス対策を構成し、デバイスを Defender for Endpoint にオンボードします。 次に、エンドポイント保護機能を構成し、Microsoft Defender ウイルス対策モードに設定し、すべてが正しく動作するように確認します。 最後に、Microsoft 以外のソリューションを削除します。

## <a name="the-migration-process"></a>移行プロセス

Defender for Endpoint への移行プロセスは、次の表に示す 3 つのフェーズに分けて実行できます。

![MDE 移行プロセス。](images/phase-diagrams/migration-phases.png)

<br/><br/>

|段階|説明|
|--|--|
|[移行の準備](switch-to-mde-phase-1.md)|準備 [フェーズ **中**](switch-to-mde-phase-1.md): <br/>1. 組織のデバイスを更新します。<br/>2. エンドポイントの Defender を取得します。<br/>3. 役割とアクセス許可を計画し、ポータルへのアクセス権をMicrosoft 365 Defenderします。<br/>4. デバイス プロキシとインターネット設定を構成して、組織のデバイスと Defender for Endpoint 間の通信を有効にします。 |
|[エンドポイントの Defender のセットアップ](switch-to-mde-phase-2.md)|セットアップ [フェーズ **中**](switch-to-mde-phase-2.md): <br/>1. デバイスを有効/再インストールMicrosoft Defender ウイルス対策パッシブ モードに設定します。<br/>2. エンドポイントの Defender を構成します。<br/>3. 既存のソリューションの除外リストに Defender for Endpoint を追加します。<br/>4. 既存のソリューションを、既存のソリューションの除外リストに追加Microsoft Defender ウイルス対策。<br/>5. デバイス グループ、コレクション、および組織単位を設定します。<br/>6. マルウェア対策ポリシーとリアルタイム保護設定を構成します。|
|[Defender for Endpoint へのオンボード](switch-to-mde-phase-3.md)|オンボード [フェーズ **中**](switch-to-mde-phase-3.md): <br/>1. デバイスを Defender for Endpoint にオンボードします。<br/>2. 検出テストを実行します。<br/>3. パッシブ モードMicrosoft Defender ウイルス対策を確認します。<br/>4. 更新プログラムを取得Microsoft Defender ウイルス対策。<br/>5. 既存のエンドポイント保護ソリューションをアンインストールします。<br/>6. Defender for Endpoint が正しく動作するようにします。|

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に含まれるもの

この移行ガイドでは、Defender for [](microsoft-defender-antivirus-in-windows-10.md) Endpoint への移行[](overview-endpoint-detection-response.md)の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。 ただし、Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。 Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。 次の表に、Defender for Endpoint の機能の概要を示します。

<br/><br/>

|機能/機能|説明|
|---|---|
|[脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)|脅威& 脆弱性の管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。|
|[攻撃面の減少](overview-attack-surface-reduction.md)|攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。|
|[次世代の保護](microsoft-defender-antivirus-in-windows-10.md)|次世代の保護には、脅威Microsoft Defender ウイルス対策マルウェアをブロックする機能が含まれています。|
|[エンドポイントでの検出と対応](overview-endpoint-detection-response.md)|エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。|
|[高度な追求](advanced-hunting-overview.md)|高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。|
|[動作ブロックと封じ込め](behavioral-blocking-containment.md)|動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。|
|[自動調査と修復](automated-investigations.md)|自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。|
|[脅威の検出サービス](microsoft-threat-experts.md)(Microsoft 脅威エキスパート)|脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。|

**詳細については、次の情報を参照してください。「Defender [for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>次のステップ

- 移行の [準備に進みます](switch-to-mde-phase-1.md)。
