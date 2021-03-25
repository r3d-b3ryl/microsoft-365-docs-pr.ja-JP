---
title: Microsoft 以外のエンドポイント ソリューションから Microsoft Defender for Endpoint への切り替え
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
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 02/11/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2c6029a1aada8f5f5fb27723c868f28c3de6f8aa
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218654"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Microsoft 以外のエンドポイント ソリューションから Microsoft Defender for Endpoint への切り替え

Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for [Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) に切り替える予定の場合は、適切な場所にいます。 この記事をガイドとして使用します。

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Defender for Endpoint への移行の概要":::

Defender for Endpoint に切り替える場合は、Microsoft 以外のソリューションをアクティブ モードで開始し、パッシブ モードで Defender for Endpoint を構成し、Defender for Endpoint にオンボードし、Defender for Endpoint をアクティブ モードに設定し、Microsoft 以外のソリューションを削除します。

> [!TIP]
> - 現在 McAfee Endpoint Security (McAfee) を使用している場合は、「Migrate from McAfee to [Microsoft Defender for Endpoint」を参照してください](mcafee-to-microsoft-defender-migration.md)。
> - 現在 Symantec Endpoint Protection (Symantec) を使用している場合は、「Migrate [from Symantec](symantec-to-microsoft-defender-endpoint-migration.md)to Microsoft Defender for Endpoint 」を参照してください。

## <a name="the-migration-process"></a>移行プロセス

Microsoft Defender for Endpoint に切り替える場合は、次の表で説明するように、3 つのフェーズに分割できるプロセスに従います。

![移行フェーズ - 準備、セットアップ、オンボード](images/phase-diagrams/migration-phases.png)

|段階 |説明 |
|--|--|
|[移行の準備](switch-to-microsoft-defender-prepare.md) |準備 [フェーズ **では** 、](switch-to-microsoft-defender-prepare.md)組織のデバイスを更新し、Microsoft Defender for Endpoint を取得し、役割とアクセス許可を計画し、Microsoft Defender セキュリティ センターへのアクセスを許可します。 また、デバイス プロキシとインターネット設定を構成して、組織のデバイスと Microsoft Defender for Endpoint 間の通信を有効にします。 |
|[エンドポイント用 Microsoft Defender のセットアップ](switch-to-microsoft-defender-setup.md) |セットアップ[](switch-to-microsoft-defender-setup.md)フェーズでは、Microsoft Defender Antivirus を有効にしてパッシブ モードに設定し、Microsoft Defender Antivirus、Microsoft Defender for Endpoint、および既存のエンドポイント保護ソリューションの設定 & 除外を構成します。 デバイス グループ、コレクション、および組織単位も作成します。 最後に、マルウェア対策ポリシーとリアルタイム保護設定を構成します。|
|[エンドポイント用 Microsoft Defender にオンボード](switch-to-microsoft-defender-onboard.md) |オンボード [フェーズ **中に** 、](switch-to-microsoft-defender-onboard.md)デバイスを Microsoft Defender for Endpoint にオンボードし、それらのデバイスが Microsoft Defender for Endpoint と通信しているのを確認します。 最後に、既存のエンドポイント保護ソリューションをアンインストールし、Microsoft Defender Antivirus &による保護がアクティブ モードに設定されている必要があります。 |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に含まれるもの

この移行ガイドでは、Microsoft Defender [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) for Endpoint[](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)への移行の開始点として、次世代の保護とエンドポイントの検出および応答機能に重点を置いています。 ただし、Microsoft Defender for Endpoint には、ウイルス対策やエンドポイント保護以外の機能が含まれています。 Microsoft Defender for Endpoint は、予防的な保護、侵害後の検出、自動調査、対応のための統一されたプラットフォームです。 次の表に、Microsoft Defender for Endpoint の機能の概要を示します。 

| 機能/機能 | 説明 |
|---|---|
| [脅威&の管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | 脅威&管理機能は、エンドポイント (デバイスなど) 全体の弱点を特定、評価、修復するのに役立ちます。 |
| [攻撃面の縮小](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | 攻撃表面の縮小ルールは、組織のデバイスとアプリケーションをサイバー脅威や攻撃から保護するのに役立ちます。 |
| [次世代の保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | 次世代の保護には、脅威やマルウェアのブロックに役立つ Microsoft Defender ウイルス対策が含まれています。 |
| [エンドポイントの検出および応答](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | エンドポイントの検出および応答機能は、侵入の試みとアクティブな侵害を検出、調査、および対応します。  |
| [高度な検出](advanced-hunting-overview.md) | 高度な検出機能により、セキュリティ運用チームは既知または潜在的な脅威のインジケーターとエンティティを検索できます。 |
| [動作のブロックと格納](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | 動作のブロックと格納機能は、脅威の実行が開始された場合でも、その動作に基づいて脅威を特定し、停止し、ツリーを処理するのに役立ちます。 |
| [調査と修復の自動化](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | 自動調査および応答機能は、アラートを調べ、侵害を解決するために直ちに修復アクションを実行します。 |
| [脅威の検出サービス](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Microsoft Threat Experts) | 脅威検出サービスは、セキュリティ運用チームに専門家レベルの監視と分析を提供し、重要な脅威を見逃しなくするために役立ちます。 |

**詳細については、次の情報を参照してください。「Microsoft [Defender for Endpoint」を参照してください](https://docs.microsoft.com/windows/security/threat-protection)。**

## <a name="next-step"></a>次の手順

- 移行の [準備に進みます](switch-to-microsoft-defender-prepare.md)。
