---
title: Microsoft Defender for Cloud Appsの評価環境を有効にする
description: Microsoft Defender for Office 365内のDefender for Cloud アプリのアーキテクチャを学習し、Microsoft 365 Defender製品間の相互作用を理解します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a66a3563d01e8e4239a0f4815fec9234fd46e1fc
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498981"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Appsの評価環境を有効にする

**適用対象:**

- Microsoft 365 Defender

この記事は、Microsoft Defender for Cloud Appsの評価環境を設定する手順 [2/2](eval-defender-mcas-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-mcas-overview.md)関する記事を参照してください。

この記事では、Defender for Cloud Apps ポータルにアクセスし、クラウド アプリのトラフィック データを収集するために必要な統合を構成するプロセスについて説明します。

環境で使用されているクラウド アプリを検出するには、次の方法のいずれかまたは両方を実装できます。

- Microsoft Defender for Endpointと統合することで、Cloud Discovery を使用して迅速に起動して実行します。 このネイティブ統合を使用すると、ネットワークのオンとオフのWindows 10およびWindows 11 デバイス間のクラウド トラフィックに関するデータの収集をすぐに開始できます。
- ネットワークに接続されているすべてのデバイスからアクセスされたすべてのクラウド アプリを検出するには、Defender for Cloud Apps ログ コレクターをファイアウォールやその他のプロキシにデプロイします。 このデプロイは、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信するのに役立ちます。 Defender for Cloud Apps は、より多くの機能を提供するために、一部のサード パーティのプロキシとネイティブに統合されます。

この記事には、両方の方法のガイダンスが含まれています。

Microsoft Defender for Cloud Appsを設定するには、次の手順に従います。

:::image type="content" source="../../media/defender/m365-defender-mcas-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境で Microsoft Microsoft Defender for Cloud Appsを有効にする手順" lightbox="../../media/defender/m365-defender-mcas-eval-enable-steps.png":::

- [手順 1.Defender for Cloud アプリ ポータルにConnectする](#step-1)
- [手順 2.Microsoft Defender for Endpointと統合する](#step-2)
- [手順 3.Defender for Cloud Apps ログ コレクターをファイアウォールやその他のプロキシにデプロイする](#step-3)
- [手順 4.Cloud Discovery ダッシュボードを表示して、組織で使用されているアプリを確認する](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>手順 1. Defender for Cloud アプリ ポータルにConnectする

ライセンスを確認し、Defender for Cloud アプリ ポータルに接続するには、「[クイック スタート: Microsoft Defender for Cloud Appsを使用した概要](/cloud-app-security/getting-started-with-cloud-app-security)」を参照してください。

ポータルにすぐに接続できない場合は、ファイアウォールの許可リストに IP アドレスを追加することが必要な場合があります。 [Defender for Cloud アプリの基本的なセットアップに関する説明を](/cloud-app-security/general-setup)参照してください。

それでも問題が解決しない場合は、 [ネットワーク要件](/cloud-app-security/network-requirements)を確認してください。

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>手順 2。 Microsoft Defender for Endpointと統合する

Microsoft Defender for Cloud Appsは、ネイティブにMicrosoft Defender for Endpointと統合されます。 この統合により、Cloud Discovery のロールアウトが簡略化され、企業ネットワークを超えて Cloud Discovery 機能が拡張され、デバイスベースの調査が可能になります。 この統合により、IT マネージド Windows 10およびWindows 11 デバイスからアクセスされるクラウド アプリとサービスが明らかにされます。

Microsoft Defender for Endpointを既に設定している場合は、Defender for Cloud Apps との統合を構成することは、Microsoft 365 Defenderのトグルです。 統合が有効になった後、Defender for Cloud Apps ポータルに戻り、Cloud Discovery ダッシュボードでリッチ データを表示できます。

これらのタスクを実行するには、[Microsoft Defender for Cloud Appsとの統合Microsoft Defender for Endpoint](/cloud-app-security/mde-integration)参照してください。

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>手順 3. Defender for Cloud Apps ログ コレクターをファイアウォールやその他のプロキシにデプロイする

ネットワークに接続されているすべてのデバイスでカバレッジを得るには、Defender for Cloud Apps ログ コレクターをファイアウォールやその他のプロキシに展開して、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信します。

次のいずれかの Secure Web Gateway (SWG) を使用している場合、Defender for Cloud Apps はシームレスなデプロイと統合を提供します。

- Zscaler
- iboss
- Corrata
- Menlo Security

これらのネットワーク デバイスとの統合の詳細については、「 [Cloud Discovery のセットアップ](/cloud-app-security/set-up-cloud-discovery)」を参照してください。

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>手順 4. Cloud Discovery ダッシュボードを表示して、組織で使用されているアプリを確認する

Cloud Discovery ダッシュボードは、組織でのクラウド アプリの使用方法に関するより詳細な分析情報を提供するように設計されています。 使用されているアプリの種類、オープン アラート、組織内のアプリのリスク レベルの概要を一目で確認できます。

Cloud Discovery ダッシュボードの使用を開始するには、「 [検出されたアプリの操作](/cloud-app-security/discovered-apps)」を参照してください。

## <a name="next-steps"></a>次の手順

手順 3/3: [パイロット Microsoft Defender for Cloud Apps](eval-defender-mcas-pilot.md)

[Microsoft Defender for Cloud Appsの評価](eval-defender-mcas-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
