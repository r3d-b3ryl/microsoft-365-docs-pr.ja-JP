---
title: Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え
description: エンドポイント保護ソリューションの機能を含む Microsoft Defender for Endpoint Microsoft Defender ウイルス対策切り替えます。
keywords: 移行、Windows Defender、高度なエンドポイント保護、ウイルス対策、マルウェア対策、パッシブ モード、アクティブ モード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 08/16/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 267787b2cacc00a1d402c2f4dd2e57f42bd3dda3
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59402168"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え

Microsoft 以外のエンドポイント保護ソリューションから [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) への切り替えについて考えている場合は、適切な場所にいます。 この記事をガイドとして使用します。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="エンドポイント保護ソリューションを Defender for Endpoint に切り替えます。":::

Defender for Endpoint に切り替える場合は、アクティブ モードで Microsoft 以外のウイルス対策/マルウェア対策保護から始まります。 次に、パッシブ モードMicrosoft Defender ウイルス対策を構成し、デバイスを Defender for Endpoint にオンボードします。 次に、エンドポイント保護機能を構成し、Microsoft Defender ウイルス対策モードに設定し、すべてが正しく動作するように確認します。 最後に、Microsoft 以外のソリューションを削除します。

## <a name="the-migration-process"></a>移行プロセス

Defender for Endpoint への移行プロセスは、次の表に示す 3 つのフェーズに分けて実行できます。

![MDE 移行プロセス。](images/phase-diagrams/migration-phases.png)

|段階|説明|
|--|--|
|[移行の準備](switch-to-microsoft-defender-prepare.md)|準備 [フェーズ **中**](switch-to-microsoft-defender-prepare.md): <ol><li>組織のデバイスを更新します。</li><li>エンドポイントの Defender を取得します。</li><li>役割とアクセス許可を計画し、ポータルへのアクセス権をMicrosoft 365 Defenderします。</li><li>デバイス プロキシとインターネット設定を構成して、組織のデバイスと Defender for Endpoint 間の通信を有効にします。</li></ol>|
|[エンドポイントの Defender のセットアップ](switch-to-microsoft-defender-setup.md)|セットアップ [フェーズ **中**](switch-to-microsoft-defender-setup.md): <ol><li>デバイスを有効/再Microsoft Defender ウイルス対策し、パッシブ モードに設定します。</li><li> エンドポイントの Defender を構成します。</li><li>既存のソリューションの除外リストに Defender for Endpoint を追加します。</li><li>既存のソリューションを、既存のソリューションの除外リストに追加Microsoft Defender ウイルス対策。</li><li>デバイス グループ、コレクション、および組織単位を設定します。</li><li>マルウェア対策ポリシーとリアルタイム保護設定を構成します。</li></ol>|
|[Defender for Endpoint へのオンボード](switch-to-microsoft-defender-onboard.md)|オンボード [フェーズ **中**](switch-to-microsoft-defender-onboard.md): <ol><li>デバイスを Defender for Endpoint にオンボードします。</li><li>検出テストを実行します。</li><li>パッシブ モードMicrosoft Defender ウイルス対策を確認します。</li><li>ユーザーの更新プログラムをMicrosoft Defender ウイルス対策。</li><li>既存のエンドポイント保護ソリューションをアンインストールします。</li><li>Defender for Endpoint が正しく動作するようにします。</li></ol>|

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
|[調査と修復の自動化](automated-investigations.md)|自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。|
|[脅威の検出サービス](microsoft-threat-experts.md)(Microsoft 脅威エキスパート)|脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。|

**詳細については、次の情報を参照してください。「Defender [for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>次の手順

- 移行の [準備に進みます](switch-to-microsoft-defender-prepare.md)。
