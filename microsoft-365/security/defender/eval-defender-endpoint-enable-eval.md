---
title: Microsoft Defender for Endpoint評価を有効にする
description: ライセンス状態の確認やエンドポイントのオンボードなど、Microsoft 365 Defender試用版ラボまたはパイロット環境を有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2acde87daaff88ec9ce7458218919342a9f1edd8
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782503"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Microsoft Defender for Endpoint評価環境を有効にする


この記事では、運用デバイスを使用してMicrosoft Defender for Endpointの評価環境を設定する手順について説明します。 


> [!TIP]
> Microsoft Defender for Endpointには、事前構成済みのデバイスを追加し、シミュレーションを実行してプラットフォームの機能を評価できる製品内評価ラボも付属しています。 ラボには、高度なハンティングや脅威分析などの多くの機能のガイダンスを含め、Microsoft Defender for Endpointの価値を迅速に示すのに役立つ簡略化されたセットアップ エクスペリエンスが付属しています。 詳細については、「機能の [評価](../defender-endpoint/evaluation-lab.md)」を参照してください。 <br> この記事で説明するガイダンスと評価ラボの主な違いは、評価環境で運用デバイスが使用されるのに対し、評価ラボでは非運用デバイスが使用されていることです。 

次の手順を使用して、Microsoft Defender for Endpointの評価を有効にします。

:::image type="content" source="../../media/defender/m365-defender-endpoint-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境でMicrosoft Defender for Endpointを有効にする手順" lightbox="../../media/defender/m365-defender-endpoint-eval-enable-steps.png":::

- [手順 1.ライセンスの状態を確認する](#step-1-check-license-state)
- [手順 2.エンドポイントをオンボードする](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>手順 1. ライセンスの状態を確認する

まず、ライセンスの状態を確認して、適切にプロビジョニングされたことを確認する必要があります。 これを行うには、管理センターまたは **Microsoft Azure ポータル** を使用します。


1. ライセンスを表示するには、**Microsoft Azure ポータル** に移動し、[Microsoft Azure ポータルのライセンス セクション](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)に移動します。

   :::image type="content" source="../../media/defender/atp-licensing-azure-portal.png" alt-text="Microsoft 365 Defender ポータルの [Azure ライセンス] ページ" lightbox="../../media/defender/atp-licensing-azure-portal.png":::

1. または、管理センターで **BillingSubscriptions** >  に移動します。

    画面に、プロビジョニングされたすべてのライセンスとその現在の **状態** が表示されます。

    :::image type="content" source="../../media/defender/atp-billing-subscriptions.png" alt-text="Microsoft Azure ポータルの [課金ライセンス] ページ" lightbox="../../media/defender/atp-billing-subscriptions.png":::
    

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>手順 2. サポートされている管理ツールのいずれかを使用してエンドポイントをオンボードする

ライセンス状態が適切にプロビジョニングされたことを確認したら、サービスへのデバイスのオンボードを開始できます。 

Microsoft Defender for Endpointを評価するために、評価を実施するWindowsデバイスをいくつか選択することをお勧めします。

サポートされている管理ツールのいずれかを使用することもできますが、Intuneは最適な統合を提供します。 詳細については、「[Microsoft IntuneでのMicrosoft Defender for Endpointの構成](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune)」を参照してください。

[「計画展開」](../defender-endpoint/deployment-strategy.md)トピックでは、Defender for Endpoint をデプロイするために必要な一般的な手順について説明します。  

このビデオでは、オンボード プロセスの概要と、使用可能なツールと方法について説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>オンボード ツールのオプション

次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールの一覧を示します。

エンドポイント | ツール オプション
:---|:---
**Windows** | [ローカル スクリプト (最大 10 台のデバイス)](../defender-endpoint/configure-endpoints-script.md)、[グループ ポリシー](../defender-endpoint/configure-endpoints-gp.md)、[Microsoft エンドポイント マネージャー/モバイル デバイス マネージャー](../defender-endpoint/configure-endpoints-mdm.md)、[Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md)、[VDI スクリプト](../defender-endpoint/configure-endpoints-vdi.md)、[との統合Microsoft Defender for Cloud](../defender-endpoint/configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)
**macOS** | [ローカル スクリプト](../defender-endpoint/mac-install-manually.md)、[Microsoft エンドポイント マネージャー](../defender-endpoint/mac-install-with-intune.md)、[JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)、[モバイル デバイス管理](../defender-endpoint/mac-install-with-other-mdm.md)
**Linux Server** | [ローカル スクリプト](../defender-endpoint/linux-install-manually.md)、  [Puppet](../defender-endpoint/linux-install-with-puppet.md)、  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [アプリベース](../defender-endpoint/ios-install.md)
**Android** | [Microsoft エンドポイント マネージャー](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>次のステップ
[Microsoft Defender for Endpointのパイロットをセットアップする](eval-defender-endpoint-pilot.md)
 
[Microsoft Defender for Endpointの評価](eval-defender-endpoint-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
