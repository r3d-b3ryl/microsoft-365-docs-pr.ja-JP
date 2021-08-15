---
title: エンドポイント評価用のパイロット Defender
description: 試用版ラボMicrosoft 365 Defenderパイロット環境を有効にする。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 873dd032b0f53b95327fcc8b517031cfed80501e55fbc74c65daf06be2f75a15
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898382"
---
# <a name="pilot-mde-evaluation"></a>パイロット MDE 評価

>[!NOTE]
>一般的な展開を案内する目的で、このシナリオでは、このシナリオでは、ユーザーの使用のみをMicrosoft Endpoint Configuration Manager。 Defender for Endpoint は、他のオンボーディング ツールの使用をサポートしていますが、展開ガイドではこれらのシナリオについては説明しません。 詳細については、「デバイスを [Microsoft Defender for Endpoint にオンボードする」を参照してください](onboard-configure.md)。

## <a name="step-1-check-license-state"></a>手順 1. ライセンスの状態を確認する

ライセンスの状態を確認し、適切にプロビジョニングされたかどうかを確認するには、管理センターまたはポータルMicrosoft Azure **できます**。

1. ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure][セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   ![[Azure ライセンス] ページのイメージ](images/atp-licensing-azure-portal.png)

1. または、管理センターで [課金サブスクリプション]   >  **に移動します**。

    画面に、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。

    ![課金ライセンスのイメージ](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 2. サポートされている管理ツールを使用したオンボード エンドポイント

「 [展開の計画」](deployment-strategy.md) トピックでは、Defender for Endpoint の展開に必要な一般的な手順について説明します。  

オンボーディング プロセスの概要と、使用可能なツールと方法について詳しくは、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

アーキテクチャを特定した後、使用する展開方法を決定する必要があります。 選択した展開ツールは、エンドポイントをサービスにオンボードする方法に影響します。

### <a name="onboarding-tool-options"></a>オンボーディング ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。

| Endpoint     | ツール オプション                       |
|--------------|------------------------------------------|
| **Windows**  |  [ローカル スクリプト (最大 10 台のデバイス)](../defender-endpoint/configure-endpoints-script.md) <br> [グループ ポリシー](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI スクリプト](../defender-endpoint/configure-endpoints-vdi.md) <br> [Azure Defender との統合](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [ローカル スクリプト](../defender-endpoint/mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [モバイル デバイス管理](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [ローカル スクリプト](../defender-endpoint/linux-install-manually.md) <br> [Puppet](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [アプリベース](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft エンドポイント マネージャー](../defender-endpoint/android-intune.md)               |
