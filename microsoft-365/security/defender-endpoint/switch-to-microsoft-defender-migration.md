---
title: Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え
description: Microsoft Defender for Endpoint に切り替えます。 概要については、この記事をお読みください。
keywords: 移行、 Windows Defender Advanced endpoint protection, for Endpoint, edr
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
ms.date: 06/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 50a2a17987c78b1a5f7aca7046a8cfd34e0ec467
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247605"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Microsoft 以外のエンドポイント保護から Microsoft Defender for Endpoint への切り替え

Microsoft 以外のエンドポイント保護ソリューションから [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) への切り替えについて考えている場合は、適切な場所にいます。 この記事をガイドとして使用します。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Defender for Endpoint への移行の概要":::

Defender for Endpoint に切り替える場合は、アクティブ モードで動作している Microsoft 以外のソリューションから始まります。 次に、パッシブ モードで Defender for Endpoint を構成し、デバイスを Defender for Endpoint にオンボードします。 次に、Defender for Endpoint をアクティブ モードに設定します。 最後に、Microsoft 以外のソリューションを削除します。

## <a name="the-migration-process"></a>移行プロセス

Defender for Endpoint への移行プロセスは、次の表に示す 3 つのフェーズに分けて実行できます。

![移行フェーズ - 準備、セットアップ、オンボード](images/phase-diagrams/migration-phases.png)

|段階 |説明 |
|--|--|
|[移行の準備](switch-to-microsoft-defender-prepare.md) |準備 [フェーズ **中**](switch-to-microsoft-defender-prepare.md): <br/>1. 組織のデバイスを更新します。 <br/>2. エンドポイントの Defender を取得します。 <br/>3. 役割とアクセス許可を計画し、ポータルへのアクセス権をMicrosoft 365 Defenderします。 <br/>4. デバイス プロキシとインターネット設定を構成して、組織のデバイスと Defender for Endpoint 間の通信を有効にします。 |
|[エンドポイントの Defender のセットアップ](switch-to-microsoft-defender-setup.md) |セットアップ [フェーズ **中**](switch-to-microsoft-defender-setup.md): <br/>1. デバイスを有効/再インストールMicrosoft Defender ウイルス対策パッシブ モードに設定します。 <br/>2. エンドポイントの Defender を構成します。 <br/>3. 既存のソリューションの除外リストに Defender for Endpoint を追加します。 <br/>4. 既存のソリューションを、既存のソリューションの除外リストに追加Microsoft Defender ウイルス対策。 <br/>5. デバイス グループ、コレクション、および組織単位を設定します。 <br/>6. マルウェア対策ポリシーとリアルタイム保護設定を構成します。|
|[Defender for Endpoint へのオンボード](switch-to-microsoft-defender-onboard.md) |オンボード [フェーズ **中**](switch-to-microsoft-defender-onboard.md): <br/>1. デバイスを Defender for Endpoint にオンボードします。 <br/>2. 検出テストを実行します。 <br/>3. パッシブ モードMicrosoft Defender ウイルス対策を確認します。 <br/>4. 更新プログラムを取得Microsoft Defender ウイルス対策。 <br/>5. 既存のエンドポイント保護ソリューションをアンインストールします。 <br/>6. Defender for Endpoint が正しく動作するようにします。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に含まれるもの

この移行ガイドでは、Defender for [](microsoft-defender-antivirus-in-windows-10.md) Endpoint への移行[](overview-endpoint-detection-response.md)の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。 ただし、Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。 Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合プラットフォームです。 次の表に、Defender for Endpoint の機能の概要を示します。 

| 機能/機能 | 説明 |
|---|---|
| [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md) | 脅威& 脆弱性の管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。 |
| [攻撃面の減少](overview-attack-surface-reduction.md) | 攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。 |
| [次世代の保護](microsoft-defender-antivirus-in-windows-10.md) | 次世代の保護には、脅威Microsoft Defender ウイルス対策マルウェアをブロックする機能が含まれています。 |
| [エンドポイントでの検出と対応](overview-endpoint-detection-response.md) | エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。  |
| [高度な追求](advanced-hunting-overview.md) | 高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。 |
| [動作ブロックと封じ込め](behavioral-blocking-containment.md) | 動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。 |
| [調査と修復の自動化](automated-investigations.md) | 自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。 |
| [脅威の検出サービス](microsoft-threat-experts.md)(Microsoft 脅威エキスパート) | 脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。 |

**詳細については、次の情報を参照してください。「Defender [for Endpoint」を参照してください](microsoft-defender-endpoint.md)。**

## <a name="next-step"></a>次の手順

- 移行の [準備に進みます](switch-to-microsoft-defender-prepare.md)。
