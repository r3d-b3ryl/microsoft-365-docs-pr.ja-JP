---
title: Microsoft Defender for Endpointから Microsoft Defender for Cloud へのサーバーの移行
description: Microsoft Defender for Endpointから Microsoft Defender for Cloud にサーバーを移行する方法について説明します。
keywords: 移行サーバー, サーバー, Microsoft Defender for Endpoint サーバー, Microsoft Defender for Cloud, MDE, azure, azure cloud, CSPM, CWP, クラウド ワークロード保護, 脅威保護, 高度な脅威保護, Microsoft Azure, マルチクラウド コネクタ
author: alekyaj
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: migrationguides
ms.date: 07/19/2022
ms.technology: mde
ms.openlocfilehash: d6ce0fe6b001c537a6bb801f18920f759a1cce09
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67109445"
---
# <a name="migrating-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Microsoft Defender for Endpointから Microsoft Defender for Cloud へのサーバーの移行

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

この記事では、サーバーを Microsoft Defender for Endpoint (MDE) から Defender for Cloud に移行する方法について説明します。

[Microsoft Defender for Endpoint](https://www.microsoft.com/security/business/endpoint-security/microsoft-defender-endpoint) (MDE) は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応できるように設計されたエンタープライズ エンドポイント セキュリティ プラットフォームです。

[Microsoft Defender for Cloud](https://azure.microsoft.com/services/defender-for-cloud/) は、クラウド構成全体の弱点を見つけるクラウド セキュリティ体制管理 (CSPM) とクラウド ワークロード保護 (CWP) 用のソリューションです。 また、環境の全体的なセキュリティ体制を強化し、進化する脅威からマルチクラウドおよびハイブリッド環境全体のワークロードを保護することもできます。

どちらの製品もサーバー保護機能を備えていますが、Microsoft Defender for Cloud は、サーバーを含むインフラストラクチャ リソースを保護するための主要なソリューションです。 

## <a name="how-do-i-migrate-my-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Microsoft Defender for Endpointから Microsoft Defender for Cloud にサーバーを移行操作方法?

Defender for Endpoint にサーバーをオンボードしている場合、移行プロセスはマシンの種類によって異なりますが、一連の共有前提条件があります。 

Microsoft Defender for Cloud は、Microsoft Azure portalのサブスクリプション ベースのサービスです。 そのため、Azure サブスクリプションで Defender for Cloud と Microsoft Defender for Servers プラン 2 などの基になるプランを有効にする必要があります。

Azure [Arc 対応](/azure/azure-arc/servers/overview)サーバーを介して接続されている Azure VM と Azure 以外のマシンに対して Defender for Servers を有効にするには、次のガイドラインに従います。

1. Azure をまだ使用していない場合は、 [Azure Well-Architected Framework](/azure/architecture/framework/) に従って環境を計画します。
2. サブスクリプションで [Microsoft Defender for Cloud](/azure/defender-for-cloud/get-started) を有効にします。
3. [サブスクリプション](/azure/defender-for-cloud/enable-enhanced-security)で Microsoft Defender for Server プランのいずれかを有効にします。 Defender for Servers プラン 2 を使用している場合は、マシンが接続されている Log Analytics ワークスペースでも有効にしてください。ファイル整合性監視、アダプティブ アプリケーション コントロールなどのオプション機能を使用できます。
4. サブスクリプションで [MDE 統合](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows) が有効になっていることを確認します。 既存の Azure サブスクリプションがある場合は、次の図に示す 2 つのオプトイン ボタンのいずれか (またはその両方) が表示される場合があります。
     :::image type="content" source="images/mde-integration.png" alt-text="MDE 統合を有効にする方法を示すスクリーンショット。":::
環境にこれらのボタンがある場合は、両方の統合を有効にしてください。 新しいサブスクリプションでは、両方のオプションが既定で有効になります。
5. Azure Arc の接続要件が満たされていることを確認します。 Microsoft Defender for Cloud では、すべてのオンプレミスマシンと Azure 以外のマシンを Azure Arc エージェント経由で接続する必要があります。 また、Azure Arc では、MDE でサポートされているすべてのオペレーティング システムがサポートされているわけではありません。 そのため、 [ここで Azure Arc デプロイ](/azure/azure-arc/servers/plan-at-scale-deployment)を計画する方法について説明します。
6. *推奨：* Defender for Cloud で脆弱性の結果を確認する場合は、Defender for Cloud の [Microsoft Defender 脆弱性の管理](/azure/defender-for-cloud/enable-data-collection?tabs=autoprovision-va)を有効にしてください。
   :::image type="content" source="images/enable-threat-and-vulnerability-management.png" alt-text="脆弱性管理を有効にする方法を示すスクリーンショット。"::: 

## <a name="how-do-i-migrate-existing-azure-vms-to-microsoft-defender-for-cloud"></a>既存の Azure VM を Microsoft Defender for Cloud に移行操作方法?

Azure VM の場合、追加の手順は必要ありません。Azure プラットフォームと Defender for Cloud のネイティブ統合により、これらは Microsoft Defender for Cloud に自動的にオンボードされます。

## <a name="how-do-i-migrate-on-premises-machines-to-microsoft-defender-for-servers"></a>オンプレミス マシンを Microsoft Defender for Servers に移行操作方法?

Azure Arc [に接続](/azure/defender-for-cloud/quickstart-onboard-machines?pivots=azure-arc)されたサーバーを介してオンプレミスのマシンを接続します。

## <a name="how-do-i-migrate-vms-from-aws-or-gcp-environments"></a>AWS または GCP 環境から VM を移行操作方法?

1. サブスクリプションに新しいマルチクラウド コネクタを作成します。 (コネクタの詳細については、「 [AWS アカウント](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings) または [GCP プロジェクト](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings)」を参照してください。
2. マルチクラウド コネクタで、 [AWS](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites) または [GCP](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings#configure-the-servers-plan) コネクタで Defender for Servers を有効にします。
3. Azure Arc エージェント、Microsoft Defender for Endpoint拡張機能、脆弱性評価、および必要に応じて Log Analytics 拡張機能のマルチクラウド コネクタで自動プロビジョニングを有効にします。
     :::image type="content" source="images/select-plans-aws-gcp.png" alt-text="Azure Arc エージェントの自動プロビジョニングを有効にする方法を示すスクリーンショット。":::
詳細については、「 [Defender for Cloud のマルチクラウド機能](https://aka.ms/mdcmc)」を参照してください。

## <a name="what-happens-once-all-migration-steps-are-completed"></a>すべての移行手順が完了するとどうなりますか?

関連する移行手順を完了すると、Microsoft Defender for Cloud は Azure Arc を介して接続されている Azure VM と Azure 以外のマシン (AWS および GCP コンピューティングの VM を含む) に拡張機能をデプロイ `MDE.Windows` します `MDE.Linux` 。

この拡張機能は、管理およびデプロイ インターフェイスとして機能し、オペレーティング システム内で MDE インストール スクリプトを調整してラップし、そのプロビジョニング状態を Azure 管理プレーンに反映します。 インストール プロセスは、既存の Defender for Endpoint のインストールを認識し、Defender for Endpoint サービス タグを自動的に追加して Defender for Cloud に接続します。

従来の Log Analytics ベースのMicrosoft Defender for Endpoint ソリューションでプロビジョニングされた R2 または 2016 マシンをWindows Server 2012している場合、Microsoft Defender for Cloud のデプロイ プロセスで Defender for Endpoint [統合ソリューション](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)がデプロイされます。 デプロイが正常に完了すると、これらのマシンで従来の Defender for Endpoint プロセスが停止され、無効になります。
