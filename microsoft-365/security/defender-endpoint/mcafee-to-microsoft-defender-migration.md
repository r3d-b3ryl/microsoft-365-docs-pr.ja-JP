---
title: McAfee から Microsoft Defender for Endpoint への移行
description: McAfee から Microsoft Defender for Endpoint に切り替えます。 概要については、この記事をお読みください。
keywords: 移行, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 3d26e2c134f5f9794f7acd41e49c27bd9f331153
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932645"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>McAfee から Microsoft Defender for Endpoint への移行

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

McAfee Endpoint Security (McAfee) から Microsoft [Defender for](https://docs.microsoft.com/windows/security/threat-protection) Endpoint (Microsoft Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。 この記事をガイドとして使用します。


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="McAfee から Defender for Endpoint への移行の概要":::

McAfee から Defender for Endpoint に切り替える場合は、アクティブ モードでマカフィー ソリューションを開始し、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、McAfee を削除します。

## <a name="the-migration-process"></a>移行プロセス

McAfee から Microsoft Defender for Endpoint に切り替える場合は、準備、セットアップ、オンボードの 3 つのフェーズに分かれるプロセスに従います。 

![移行フェーズ - セットアップをオンボードで準備する](images/phase-diagrams/migration-phases.png)

|段階 |説明 |
|--|--|
|[移行の準備](mcafee-to-microsoft-defender-prepare.md) |準備フェーズ [**では**](mcafee-to-microsoft-defender-prepare.md) 、組織のデバイスを更新し、Microsoft Defender for Endpoint を取得し、役割とアクセス許可を計画し、Microsoft Defender セキュリティ センターへのアクセスを許可します。 また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Microsoft Defender for Endpoint 間の通信を有効にします。 |
|[エンドポイント用 Microsoft Defender のセットアップ](mcafee-to-microsoft-defender-setup.md) |セットアップ フェーズ [**では**](mcafee-to-microsoft-defender-setup.md) 、Microsoft Defender ウイルス対策を有効にしてパッシブ モードに設定し、Microsoft Defender ウイルス対策、Microsoft Defender for Endpoint、McAfee の設定 & 除外を構成します。 デバイス グループ、コレクション、および組織単位も作成します。 最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。|
|[エンドポイント用 Microsoft Defender にオンボード](mcafee-to-microsoft-defender-onboard.md) |オンボード フェーズ [**中に**](mcafee-to-microsoft-defender-onboard.md) 、デバイスを Microsoft Defender for Endpoint にオンボードし、それらのデバイスが Microsoft Defender for Endpoint と通信しているのを確認します。 最後に、McAfee をアンインストールし、Microsoft Defender ウイルス対策ツールを使用した保護& Microsoft Defender for Endpoint がアクティブ モードに設定されている必要があります。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に含まれるもの

この移行ガイドでは、Microsoft Defender [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) for Endpoint[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)への移行の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。 ただし、Microsoft Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。 Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。 次の表に、Microsoft Defender for Endpoint の機能の概要を示します。 

| 機能/機能 | 説明 |
|---|---|
| [脅威と脆弱性の管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | 脅威&管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。 |
| [攻撃面の減少](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | 攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。 |
| [次世代の保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | 次世代の保護には、脅威やマルウェアのブロックに役立つ Microsoft Defender ウイルス対策が含まれています。 |
| [エンドポイントでの検出と対応](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。  |
| [高度な追求](advanced-hunting-overview.md) | 高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。 |
| [動作ブロックと封じ込め](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | 動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。 |
| [調査と修復の自動化](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | 自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。 |
| [脅威の検出サービス](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | 脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。 |

**詳細については、次の情報を参照してください。「Microsoft [Defender for Endpoint」を参照してください](https://docs.microsoft.com/windows/security/threat-protection)。**

## <a name="next-step"></a>次の手順

- 移行の [準備に進みます](mcafee-to-microsoft-defender-prepare.md)。
