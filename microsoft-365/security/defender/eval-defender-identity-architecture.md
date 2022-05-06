---
title: Microsoft Defender for Identityのアーキテクチャ要件と技術フレームワークを確認する
description: Microsoft 365 DefenderのMicrosoft Defender for Identityの技術図は、試用版ラボまたはパイロット環境を構築する前に、Microsoft 365の ID を理解するのに役立ちます。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: de49205fe20cd5685279c0a5f9d138147f24bb8d
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754160"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Microsoft Defender for Identityのアーキテクチャ要件と主要な概念を確認する


**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Identityの評価環境を設定する手順 [1/3](eval-defender-identity-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-identity-overview.md)関する記事を参照してください。

Microsoft Defender for Identityを有効にする前に、アーキテクチャを理解し、要件を満たすことができることを確認してください。

Microsoft Defender for Identityでは、機械学習と行動分析を使用して、オンプレミス ネットワーク全体の攻撃を特定し、クラウド ID に関連するユーザー サインイン リスクを検出して予防的に防止します。 詳細については、「[Microsoft Defender for Identityとは」](/defender-for-identity/what-is)を参照してください。

Defender for Identity は、Azure Active Directory (Azure AD) に同期されたオンプレミスの Active Directoryユーザーまたはユーザーを保護します。 Azure AD ユーザーのみで構成される環境を保護するには、「[Azure AD Identity Protection」を](/azure/active-directory/identity-protection/overview-identity-protection)参照してください。

## <a name="understand-the-architecture"></a>アーキテクチャを理解する

次の図は、Defender for Identity のベースライン アーキテクチャを示しています。 

:::image type="content" source="../../media/defender/m365-defender-identity-architecture.png" alt-text="Microsoft Defender for Identityの ID アーキテクチャ" lightbox="../../media/defender/m365-defender-identity-architecture.png":::

この図について:

- AD ドメイン コントローラーにインストールされているセンサーは、ログとネットワーク トラフィックを解析し、分析とレポートのためにMicrosoft Defender for Identityに送信します。
-  また、フェデレーション認証 (図の点線) を使用するようにAzure ADが構成されている場合、センサーはActive Directory フェデレーション サービス (AD FS) (AD FS) を解析することもできます。 
- Microsoft Defender for Identityは、拡張検出と応答 (XDR) のためにMicrosoft 365 Defenderにシグナルを共有します。

Defender for Identity センサーは、次のサーバーに直接インストールできます。

- ドメイン コントローラー: センサーは、専用サーバーやポート ミラーリングの構成を必要とせずに、ドメイン コントローラーのトラフィックを直接監視します。
- AD FS: センサーは、ネットワーク トラフィックと認証イベントを直接監視します。

Defender for Cloud アプリとの統合を含む Defender for Identity のアーキテクチャの詳細については、「[Microsoft Defender for Identity アーキテクチャ」を参照してください](/defender-for-identity/architecture)。


## <a name="understand-key-concepts"></a>主要な概念を理解する

次の表では、Microsoft Defender for Identityを評価、構成、デプロイするときに理解するために重要な重要な概念を示します。

|概念  |説明 |詳細情報  |
|---------|---------|---------|
| 監視対象のアクティビティ | Defender for Identity は、組織内から生成されたシグナルを監視して、疑わしいアクティビティや悪意のあるアクティビティを検出し、潜在的な脅威の有効性を判断し、効果的にトリアージして対応できるようにします。  |  [監視Microsoft Defender for Identityアクティビティ](/defender-for-identity/monitored-activities)       |
| セキュリティの警告    | Defender for Identity セキュリティ アラートでは、ネットワーク上のセンサーによって検出された不審なアクティビティと、各脅威に関連するアクターやコンピューターについて説明します。   | [Microsoft Defender for Identity セキュリティ アラート](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| エンティティ プロファイル    | エンティティ プロファイルは、ユーザー、コンピューター、デバイス、およびリソースとそのアクセス履歴に関する包括的な詳細な調査を提供します。   | [エンティティ プロファイルについて](/defender-for-identity/entity-profiles)  |
| 横移動パス    | MDI セキュリティ分析情報の重要なコンポーネントは、攻撃者が機密性の低いアカウントを使用してネットワーク全体の機密アカウントまたはマシンにアクセスする横移動パスを特定することです。  | [Microsoft Defender for Identity横移動パス (LMP)](/defender-for-identity/use-case-lateral-movement-path)  |
| ネットワーク名解決    |  ネットワーク名解決 (NNR) は、ネットワーク トラフィック、Windows イベント、ETW などに基づいてアクティビティをキャプチャし、この生データを各アクティビティに関連する関連コンピューターに関連付ける MDI 機能のコンポーネントです。       | [ネットワーク名解決とは](/defender-for-identity/nnr-policy)      |
| レポート    | Defender for Identity レポートを使用すると、システムとエンティティの状態情報を提供するレポートをスケジュールまたはすぐに生成してダウンロードできます。  環境内で検出されたシステム正常性、セキュリティ アラート、および潜在的な横移動パスに関するレポートを作成できます。   | [Microsoft Defender for Identity レポート](/defender-for-identity/reports)       |
| 役割グループ    | Defender for Identity は、管理者、ユーザー、閲覧者を含む組織固有のセキュリティとコンプライアンスのニーズに応じて、ロールベースのグループと委任されたアクセスを提供し、データを保護します。        |  [Microsoft Defender for Identity の役割グループ](/defender-for-identity/role-groups)       |
| 管理ポータル    |  Microsoft 365 Defender ポータルに加えて、Defender for Identity ポータルを使用して、疑わしいアクティビティを監視して応答できます。      | [Microsoft Defender for Identity ポータルとの連携](/defender-for-identity/workspace-portal)        |
| Microsoft Defender for Cloud Apps統合   | Microsoft Defender for Cloud Appsは、Microsoft Defender for Identityと統合して、クラウド アプリとオンプレミスの両方のハイブリッド環境全体でユーザー エンティティ行動分析 (UEBA) を提供します   | Microsoft Defender for Identity統合  |

## <a name="review-prerequisites"></a>前提条件を確認する

Defender for Identity には、オンプレミスの ID とネットワーク コンポーネントが最小要件を満たしていることを確認するための前提条件が必要です。 この記事をチェックリストとして使用して、環境の準備が整っていることを確認します。[前提条件Microsoft Defender for Identity](/defender-for-identity/prerequisites)。


## <a name="next-steps"></a>次の手順

手順 2/3: [評価環境 Defender for Identity を有効にする](eval-defender-identity-enable-eval.md)

[Microsoft Defender for Identityの評価](eval-defender-identity-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る 
