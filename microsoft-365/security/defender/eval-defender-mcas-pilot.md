---
title: パイロット Microsoft Cloud App Security、Microsoft 365 Defenderグループの作成、条件付きアクセス制御の構成、機能の試し、テストの一部としてのセットアップを行Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 672b01258c68f1cbcbfe3e2315c4b7cbcb36021e
ms.sourcegitcommit: bef7bd019531317d083c1125f7d339750c450b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587947"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>パイロット Microsoft Cloud App SecurityとMicrosoft 365 Defender


**適用対象:**
- Microsoft 365 Defender

この記事は、ユーザーの評価環境をセットアップするプロセスの手順[3/3](eval-defender-mcas-overview.md) Microsoft Cloud App Security。 このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-mcas-overview.md)。

次の手順を使用して、パイロットをセットアップして構成Microsoft Cloud App Security。


![パイロットの手順Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- 手順 1. [パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [手順 2.保護の構成 - 条件付きアクセス アプリ制御](#step-2-configure-protection--conditional-access-app-control)
- [手順 3.機能を試す - 環境を保護するためのチュートリアルの詳細](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>手順 1. パイロット グループの作成 - パイロット展開を特定のユーザー グループにスコープ設定する

Microsoft Cloud App Securityを使用すると、展開の範囲を指定できます。 スコープを使用すると、アプリの監視対象または監視から除外する特定のユーザー グループを選択できます。 ユーザー グループを含めるか除外できます。 パイロット展開の範囲を設定するには [、「Scoped Deployment」を参照してください](/cloud-app-security/scoped-deployment)。


## <a name="step-2-configure-protection--conditional-access-app-control"></a>手順 2. 保護の構成 - 条件付きアクセス アプリ制御

構成できる最も強力な保護の 1 つは、条件付きアクセス アプリ制御です。 これには、Azure Active Directory (Azure AD) との統合が必要です。 これにより、関連するポリシー (正常なデバイスの要求など) を含む条件付きアクセス ポリシーを、承認したクラウド アプリに適用できます。 

SaaS アプリをMicrosoft Cloud App Securityする最初の手順は、これらのアプリを検出し、それらを Azure AD テナントにADです。 検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](/cloud-app-security/tutorial-shadow-it)。 アプリを検出した後、これらのアプリを [Azure ADテナントに追加します](/azure/active-directory/manage-apps/add-application-portal)。

これらを管理するには、次の手順を実行します。

- まず、Azure ADで、新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。 これにより、要求がサーバーにリダイレクトCloud App Security。 1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。
- 次に、[セッション ポリシー Cloud App Security作成します。 適用するコントロールごとに 1 つのポリシーを作成します。

サポートされているアプリとクライアントを含む詳細については、「アプリを条件付きアクセス アプリ制御で保護Microsoft Cloud App Security[を参照してください](/cloud-app-security/proxy-intro-aad)。 

ポリシーの例については[、「SaaS アプリMicrosoft Cloud App Security推奨されるポリシー」を参照してください](../office-365-security/mcas-saas-access-policies.md)。 これらのポリシーは、すべての顧客の開始[](../office-365-security/microsoft-365-policies-configurations.md)点として推奨される一連の一般的な ID およびデバイス アクセス ポリシーに基になります。 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>手順 3. 機能を試す - 環境を保護するためのチュートリアルの詳細 

このMicrosoft Cloud App Securityには、リスクの発見と環境の保護に役立つ一連のチュートリアルが含まれています。 

次のチュートリアルCloud App Security試してください。

- [疑わしいユーザーアクティビティを検出する](/cloud-app-security/tutorial-suspicious-activity)
- [リスクの高いユーザーを調査する](/cloud-app-security/tutorial-ueba)
- [危険な OAuth アプリを調査する](/cloud-app-security/investigate-risky-oauth)
- [機密情報の検出と保護](/cloud-app-security/tutorial-dlp)
- [組織内のすべてのアプリをリアルタイムで保護する](/cloud-app-security/tutorial-proxy)
- [機密情報のダウンロードをブロックする](/cloud-app-security/use-case-proxy-block-session-aad)
- [管理検疫でファイルを保護する](/cloud-app-security/use-case-admin-quarantine)
- [リスクの高いアクション時にステップ アップ認証を要求する](/cloud-app-security/tutorial-step-up-authentication)

データの高度な検索の詳細についてはMicrosoft Cloud App Securityビデオを参照[してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)。

## <a name="next-steps"></a>次のステップ

[パイロット環境で、Microsoft 365 Defenderを使用して調査と対応を行う](eval-defender-investigate-respond.md)

[評価] の概要[に戻Microsoft Cloud App Security](eval-defender-mcas-overview.md)

[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)
