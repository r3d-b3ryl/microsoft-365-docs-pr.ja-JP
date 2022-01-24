---
title: パイロット Microsoft Defender for Cloud Apps with Microsoft 365 Defender
description: デバイス、ID、Microsoft 365 Defenderアプリケーションを保護するように設計されたセキュリティ ソリューションをテストおよびエクスペリエンスするために、テストラボまたはパイロット環境をセットアップします。
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
ms.openlocfilehash: 484924d936f348fb29421b6bcc1789df4a44dc90
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172405"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>パイロット Microsoft Defender for Cloud Apps with Microsoft 365 Defender


**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Cloud Apps の評価環境をセットアップするプロセスの手順 [3/3](eval-defender-mcas-overview.md) です。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-mcas-overview.md)。

次の手順を使用して、Microsoft Defender for Cloud Apps のパイロットを設定および構成します。


![Microsoft Defender for Cloud Apps のパイロット手順。](../../media/defender/m365-defender-mcas-pilot-steps.png)

- 手順 1. [パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [手順 2.保護の構成 - 条件付きアクセス アプリ制御](#step-2-configure-protection--conditional-access-app-control)
- [手順 3.機能を試す - 環境を保護するためのチュートリアルの詳細](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>手順 1. パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する

Microsoft Defender for Cloud Apps を使用すると、展開の範囲を指定できます。 スコープを使用すると、アプリの監視対象または監視から除外する特定のユーザー グループを選択できます。 ユーザー グループを含めるか除外できます。 パイロット展開の範囲を設定するには [、「Scoped Deployment」を参照してください](/cloud-app-security/scoped-deployment)。


## <a name="step-2-configure-protection--conditional-access-app-control"></a>手順 2. 保護の構成 - 条件付きアクセス アプリ制御

構成できる最も強力な保護の 1 つは、条件付きアクセス アプリ制御です。 これには、Azure Active Directory (Azure AD) との統合が必要です。 これにより、関連するポリシー (正常なデバイスの要求など) を含む条件付きアクセス ポリシーを、承認したクラウド アプリに適用できます。 

Microsoft Defender for Cloud Apps を使用して SaaS アプリを管理する最初の手順は、これらのアプリを検出し、それらをクラウド テナントAzure ADです。 検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](/cloud-app-security/tutorial-shadow-it)。 アプリを検出した後、これらのアプリを[テナントにAzure ADします](/azure/active-directory/manage-apps/add-application-portal)。

これらを管理するには、次の手順を実行します。

- 最初に、Azure AD条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。 これにより、要求が Defender for Cloud Apps にリダイレクトされます。 1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。
- 次に、[Defender for Cloud Apps] でセッション ポリシーを作成します。 適用するコントロールごとに 1 つのポリシーを作成します。

サポートされているアプリとクライアントを含む詳細については、「Microsoft Defender for Cloud Apps 条件付きアクセス アプリ制御を使用してアプリを [保護する」を参照してください](/cloud-app-security/proxy-intro-aad)。 

ポリシーの例については [、「SaaS アプリの推奨 Microsoft Defender for Cloud Apps ポリシー」を参照してください](../office-365-security/mcas-saas-access-policies.md)。 これらのポリシーは、すべての顧客の開始[](../office-365-security/microsoft-365-policies-configurations.md)点として推奨される一連の一般的な ID およびデバイス アクセス ポリシーに基になります。 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>手順 3. 機能を試す - 環境を保護するためのチュートリアルの詳細 

Microsoft Defender for Cloud Apps のドキュメントには、リスクの発見と環境の保護に役立つ一連のチュートリアルが含まれています。 

Defender for Cloud Apps のチュートリアルを試してみてください。

- [疑わしいユーザーアクティビティを検出する](/cloud-app-security/tutorial-suspicious-activity)
- [リスクの高いユーザーを調査する](/cloud-app-security/tutorial-ueba)
- [危険な OAuth アプリを調査する](/cloud-app-security/investigate-risky-oauth)
- [機密情報の検出と保護](/cloud-app-security/tutorial-dlp)
- [組織内のすべてのアプリをリアルタイムで保護する](/cloud-app-security/tutorial-proxy)
- [機密情報のダウンロードをブロックする](/cloud-app-security/use-case-proxy-block-session-aad)
- [管理検疫でファイルを保護する](/cloud-app-security/use-case-admin-quarantine)
- [リスクの高いアクション時にステップ アップ認証を要求する](/cloud-app-security/tutorial-step-up-authentication)

Microsoft Defender for Cloud Apps データでの高度な検索の詳細については、ビデオを参照 [してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。

## <a name="next-steps"></a>次の手順

[パイロット環境で、Microsoft 365 Defenderを使用して調査と対応を行う](eval-defender-investigate-respond.md)

「Microsoft Defender [for Cloud Apps の評価」の概要に戻る](eval-defender-mcas-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)
