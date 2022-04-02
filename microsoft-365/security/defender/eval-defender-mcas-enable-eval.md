---
title: Microsoft Defender for Cloud Apps の評価環境を有効にする
description: Microsoft Defender 内の Defender for Cloud Apps のアーキテクチャについて説明し、Office 365製品間の相互作用Microsoft 365 Defenderします。
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
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps の評価環境を有効にする

**適用対象:**

- Microsoft 365 Defender

この記事は [、Microsoft Defender for](eval-defender-mcas-overview.md) Cloud Apps の評価環境をセットアップするプロセスの手順 2/2 です。 このプロセスの詳細については、概要の記事を [参照してください](eval-defender-mcas-overview.md)。

この記事では、Defender for Cloud Apps ポータルにアクセスし、クラウド アプリのトラフィック データを収集するために必要な統合を構成するプロセスについて説明します。

環境で使用されているクラウド アプリを検出するには、次の方法の 1 つまたは両方を実装できます。

- Microsoft Defender for Endpoint と統合することで、クラウド探索を迅速に実行できます。 このネイティブ統合により、ネットワークのオンとオフを切り替えて、Windows 10デバイスWindowsクラウド トラフィックのデータ収集をすぐに開始できます。
- ネットワークに接続されているすべてのデバイスがアクセスしているすべてのクラウド アプリを検出するには、ファイアウォールや他のプロキシに Defender for Cloud Apps ログ コレクターを展開します。 この展開は、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信するのに役立ちます。 Defender for Cloud Apps は、さらに多くの機能を提供するために、一部のサードパーティ プロキシとネイティブに統合されます。

この記事には、両方の方法のガイダンスが含まれています。

Microsoft Defender for Cloud Apps をセットアップするには、次の手順を実行します。

:::image type="content" source="../../media/defender/m365-defender-mcas-eval-enable-steps.png" alt-text="Microsoft Defender 評価環境で Microsoft Microsoft Defender for Cloud Apps を有効にする手順" lightbox="../../media/defender/m365-defender-mcas-eval-enable-steps.png":::

- [手順 1.Connect Defender for Cloud Apps ポータルにアクセスする](#step-1)
- [手順 2.エンドポイント向け Microsoft Defender との統合](#step-2)
- [手順 3.ファイアウォールや他のプロキシに Defender for Cloud Apps ログ コレクターを展開する](#step-3)
- [手順 4.クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する](#step-4)

<a name="step-1"></a>

## <a name="step-1-connect-to-the-defender-for-cloud-apps-portal"></a>手順 1. Connect Defender for Cloud Apps ポータルにアクセスする

ライセンスを確認し、Defender for Cloud Apps ポータルに接続するには、「 [Quickstart: Get started with Microsoft Defender for Cloud Apps」を参照してください](/cloud-app-security/getting-started-with-cloud-app-security)。

ポータルにすぐに接続できない場合は、ファイアウォールの許可リストに IP アドレスを追加する必要があります。 「 [Defender for Cloud Apps の基本セットアップ」を参照してください](/cloud-app-security/general-setup)。

それでも問題が発生する場合は、「ネットワーク要件 [」を確認してください](/cloud-app-security/network-requirements)。

<a name="step-2"></a>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>手順 2. エンドポイント向け Microsoft Defender との統合

Microsoft Defender for Cloud Apps は、Microsoft Defender for Endpoint とネイティブに統合されます。 この統合により、クラウド探索のロールアウトが簡素化され、クラウド探索機能が企業ネットワークを超えて拡張され、デバイスベースの調査が可能です。 この統合により、11 台のデバイスから IT 管理されたアプリとサービスWindows 10、Windowsが明らかになります。

Microsoft Defender for Endpoint を既にセットアップしている場合は、Defender for Cloud Apps との統合を構成する方法は、Microsoft 365 Defender。 統合が有効になったら、Defender for Cloud Apps ポータルに戻り、クラウド探索ダッシュボードでリッチ データを表示できます。

これらのタスクを実行するには、「 [Microsoft Defender for Endpoint と Microsoft Defender for Cloud Apps との統合」を参照してください](/cloud-app-security/mde-integration)。

<a name="step-3"></a>

## <a name="step-3-deploy-the-defender-for-cloud-apps-log-collector-on-your-firewalls-and-other-proxies"></a>手順 3. ファイアウォールや他のプロキシに Defender for Cloud Apps ログ コレクターを展開する

ネットワークに接続されているすべてのデバイスのカバレッジについては、ファイアウォールや他のプロキシに Defender for Cloud Apps ログ コレクターを展開して、エンドポイントからデータを収集し、分析のために Defender for Cloud Apps に送信します。

次のいずれかの Secure Web Gateway (SWG) を使用している場合、Defender for Cloud Apps はシームレスな展開と統合を提供します。

- Zscaler
- iboss
- Corrata
- Menlo Security

これらのネットワーク デバイスとの統合の詳細については、「 [Set up Cloud Discovery」を参照してください](/cloud-app-security/set-up-cloud-discovery)。

<a name="step-4"></a>

## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>手順 4. クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する

クラウド検出ダッシュボードは、組織内でのクラウド アプリの使用方法に関する詳細な情報を提供するように設計されています。 使用されているアプリの種類、開いているアラート、組織内のアプリのリスク レベルの概要を一目で確認できます。

クラウド探索ダッシュボードの使用を開始するには、「検出されたアプリの操作 [」を参照してください](/cloud-app-security/discovered-apps)。

## <a name="next-steps"></a>次の手順

手順 3 /3: [クラウド アプリ用 Microsoft Defender のパイロット](eval-defender-mcas-pilot.md)

「Microsoft [Defender for Cloud Apps の評価」の概要に戻る](eval-defender-mcas-overview.md)

[評価とパイロット] [の概要に戻Microsoft 365 Defender](eval-overview.md)
