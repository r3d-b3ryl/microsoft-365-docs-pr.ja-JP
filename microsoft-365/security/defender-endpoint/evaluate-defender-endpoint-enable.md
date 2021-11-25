---
title: エンドポイント評価用のパイロット Defender
description: 試用版ラボMicrosoft 365 Defenderパイロット環境を有効にする。
keywords: Microsoft 365 Defender試し、テストMicrosoft 365 Defender、評価Microsoft 365 Defender、Microsoft 365 Defenderラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な狩猟
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 39af377ce71cf1ba8e5e19e8fa786ef9498ab96f
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167828"
---
# <a name="pilot-mde-evaluation"></a>パイロット MDE 評価

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!NOTE]
> 一般的な展開を案内する目的で、このシナリオでは、このシナリオでは、ユーザーの使用のみをMicrosoft Endpoint Configuration Manager。 Defender for Endpoint は、他のオンボーディング ツールの使用をサポートしていますが、展開ガイドではこれらのシナリオについては説明しません。 詳細については、「デバイスを [Microsoft Defender for Endpoint にオンボードする」を参照してください](onboard-configure.md)。

## <a name="step-1-check-license-state"></a>手順 1. ライセンスの状態を確認する

ライセンスの状態を確認し、適切にプロビジョニングされたかどうかを確認するには、管理センターまたはポータルMicrosoft Azure **できます**。

1. ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure][セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![[Azure ライセンス] ページのイメージ。](images/atp-licensing-azure-portal.png)

1. または、管理センターで [課金サブスクリプション]  \> **に移動します**。

    画面に、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。

    ![課金ライセンスのイメージ。](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 2。 サポートされている管理ツールを使用したオンボード エンドポイント

「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。

オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

アーキテクチャを特定した後、使用する展開方法を決定する必要があります。 選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。

### <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

<br>

****

|エンドポイント|ツール オプション|
|---|---|
|**Windows**|[ローカル スクリプト (最大 10 台のデバイス)](../defender-endpoint/configure-endpoints-script.md) <p> [グループ ポリシー](../defender-endpoint/configure-endpoints-gp.md) <p> [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](../defender-endpoint/configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <p> [VDI スクリプト](../defender-endpoint/configure-endpoints-vdi.md) <p> [Microsoft Defender for Cloudとの統合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
|**macOS**|[ローカル スクリプト](../defender-endpoint/mac-install-manually.md) <p> [Microsoft エンドポイント マネージャー](../defender-endpoint/mac-install-with-intune.md) <p> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <p> [モバイル デバイス管理](../defender-endpoint/mac-install-with-other-mdm.md)|
|**Linux Server**|[ローカル スクリプト](../defender-endpoint/linux-install-manually.md) <p> [Puppet](../defender-endpoint/linux-install-with-puppet.md) <p> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
|**iOS**|[アプリベース](../defender-endpoint/ios-install.md)|
|**Android**|[Microsoft エンドポイント マネージャー](../defender-endpoint/android-intune.md)|
|
