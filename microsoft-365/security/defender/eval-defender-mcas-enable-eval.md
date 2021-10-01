---
title: ユーザーの評価環境を有効Microsoft Cloud App Security
description: Microsoft Defender 内の MCAS のアーキテクチャについて説明し、Office 365製品間の相互作用をMicrosoft 365 Defenderします。
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c36e0f9841d0b1e95d17734047a1ad9f35d3739c
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042592"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>ユーザーの評価環境を有効Microsoft Cloud App Security


**適用対象:**

- Microsoft 365 Defender

この記事は、ユーザーの評価環境をセットアップするプロセスの手順[2/2](eval-defender-mcas-overview.md) Microsoft Cloud App Security。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-mcas-overview.md)。

この記事では、クラウド アプリのトラフィック データを収集するために、Cloud App Securityポータルにアクセスし、必要な統合を構成するプロセスについて説明します。

環境で使用されているクラウド アプリを検出するには、次の 1 つまたは両方を実行できます。

- Microsoft Defender for Endpoint と統合することで、クラウド探索を迅速に実行できます。 このネイティブ統合により、ネットワークのオンとオフを切り替えて、Windows 10デバイスWindowsクラウド トラフィックのデータ収集をすぐに開始できます。
- ネットワークに接続されているすべてのデバイスがアクセスしているすべてのクラウド アプリを検出するには、ファイアウォールや他のプロキシに Cloud App Security ログ コレクターを展開します。 これにより、エンドポイントからデータが収集され、分析Cloud App Security送信されます。 Cloud App Security機能を強化するために、一部のサード パーティ製プロキシとネイティブに統合できます。

この記事には、両方の方法のガイダンスが含まれています。

次の手順を使用して、Microsoft Cloud App Security。

![Microsoft Defender 評価環境で Microsoft Microsoft Cloud App Securityを有効にする手順。](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [手順 1.ConnectポータルにCloud App Securityする](#step-1-connect-to-the-cloud-app-security-portal)
- [手順 2.エンドポイント向け Microsoft Defender との統合](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [手順 3.ファイアウォールやCloud App Securityプロキシにログ コレクターを展開する](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [手順 4.クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>手順 1。 ConnectポータルにCloud App Securityする

ライセンスを確認し、Cloud App Security ポータルに接続するには[、「Quickstart: Get started with Microsoft Cloud App Security」 を参照してください](/cloud-app-security/getting-started-with-cloud-app-security)。 

ポータルにすぐに接続できない場合は、ファイアウォールの許可リストに IP アドレスを追加する必要があります。 詳細については[、「基本セットアップ」を参照Cloud App Security。](/cloud-app-security/general-setup)

それでも問題が発生する場合は、「ネットワーク要件 [」を確認してください](/cloud-app-security/network-requirements)。

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>手順 2。 エンドポイント向け Microsoft Defender との統合

Microsoft Cloud App Security Microsoft Defender for Endpoint とネイティブに統合されます。 この統合により、クラウド探索のロールアウトが簡素化され、クラウド探索機能が企業ネットワークを超えて拡張され、デバイスベースの調査が可能です。 この統合により、11 台のデバイスから IT 管理されたデバイスからアクセスWindows 10クラウド Windowsが明らかになります。 

Microsoft Defender for Endpoint を既にセットアップしている場合は、Cloud App Securityとの統合を構成Microsoft 365 Defender。 統合が有効になったら、ポータルに戻り、Cloud App Securityダッシュボードでリッチ データを表示できます。

これらのタスクを実行するには[、「Microsoft Defender for Endpoint と](/cloud-app-security/mde-integration)エンドポイントの統合」を参照Microsoft Cloud App Security。 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>手順 3. ファイアウォールやCloud App Securityプロキシにログ コレクターを展開する

ネットワークに接続されているすべてのデバイスでカバレッジを設定するには、ファイアウォールや他のプロキシに Cloud App Security ログ コレクターを展開して、エンドポイントからデータを収集し、分析のために Cloud App Security に送信します。 

次のいずれかの Secure Web Gateway (SWG) を使用している場合は、Cloud App Securityの展開と統合が提供されます。
- Zscaler
- iboss
- Corrata
- Menlo Security

これらのネットワーク デバイスとの統合の詳細については [、「Set up Cloud Discovery 」を参照してください](/cloud-app-security/set-up-cloud-discovery)。 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>手順 4. クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する

クラウド検出ダッシュボードは、組織内でのクラウド アプリの使用方法に関する詳細な情報を提供するように設計されています。 使用されているアプリの種類、開いているアラート、組織内のアプリのリスク レベルの概要を一目で確認できます。 

クラウド検出ダッシュボードの使用を開始するには、「検出されたアプリの操作 [」を参照してください](/cloud-app-security/discovered-apps)。

## <a name="next-steps"></a>次の手順

手順 3/ 3:[パイロット Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

[評価] の概要[に戻Microsoft Cloud App Security](eval-defender-mcas-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)