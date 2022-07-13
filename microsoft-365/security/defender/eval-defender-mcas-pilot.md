---
title: Microsoft 365 Defenderを使用したパイロット Microsoft Defender for Cloud Apps
description: デバイス、ID、データ、およびアプリケーションを保護するように設計されたセキュリティ ソリューションをテストして体験するために、Microsoft 365 Defender試用版またはパイロット環境を設定します。
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
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7dbf9154769ab4b97c15dc5fc67593b376ab2f6d
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750344"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>Microsoft 365 Defenderを使用したパイロット Microsoft Defender for Cloud Apps


**適用対象:**
- Microsoft 365 Defender

この記事は、Microsoft Defender for Cloud Appsの評価環境を設定する手順 [3/3](eval-defender-mcas-overview.md) です。 このプロセスの詳細については、 [概要に](eval-defender-mcas-overview.md)関する記事を参照してください。

次の手順に従って、Microsoft Defender for Cloud Appsのパイロットを設定して構成します。


:::image type="content" source="../../media/defender/m365-defender-mcas-pilot-steps.png" alt-text="Microsoft Defender for Cloud Appsをパイロット化する手順" lightbox="../../media/defender/m365-defender-mcas-pilot-steps.png":::
- [手順 1.パイロット グループを作成する - パイロット展開のスコープを特定のユーザー グループに設定する](#step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups)
- [手順 2.保護の構成 - 条件付きアクセス アプリ制御](#step-2-configure-protectionconditional-access-app-control)
- [手順 3.機能を試す - 環境を保護するためのチュートリアルについて説明します](#step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment) 

## <a name="step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups"></a>手順 1。 パイロット グループを作成する - パイロット展開のスコープを特定のユーザー グループに設定する

Microsoft Defender for Cloud Appsを使用すると、デプロイのスコープを設定できます。 スコープを使用すると、アプリの監視対象または監視から除外する特定のユーザー グループを選択できます。 ユーザー グループを含めたり除外したりできます。 パイロットデプロイのスコープを設定するには、「 [スコープ付きデプロイ](/cloud-app-security/scoped-deployment)」を参照してください。


## <a name="step-2-configure-protectionconditional-access-app-control"></a>手順 2。 保護の構成 - 条件付きアクセス アプリ制御

構成できる最も強力な保護の 1 つは、条件付きアクセス アプリ制御です。 この保護には、Azure Active Directory (Azure AD) との統合が必要です。 これにより、条件付きアクセス ポリシー (関連ポリシー (正常なデバイスの要求など) を含む) を、承認されたクラウド アプリに適用できます。 

Microsoft Defender for Cloud Appsを使用して SaaS アプリを管理する最初の手順は、これらのアプリを検出してから Azure AD テナントに追加することです。 検出に関するヘルプが必要な場合は、 [ネットワーク内の SaaS アプリの検出と管理に関するページを参照してください](/cloud-app-security/tutorial-shadow-it)。 アプリを検出したら、 [これらのアプリを Azure AD テナントに追加します](/azure/active-directory/manage-apps/add-application-portal)。

これらのアプリの管理を開始するには、次のタスクを実行します。

- まず、Azure AD で新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。 この構成は、Defender for Cloud Apps に要求をリダイレクトするのに役立ちます。 1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。
- 次に、Defender for Cloud Apps でセッション ポリシーを作成します。 適用するコントロールごとに 1 つのポリシーを作成します。

サポートされているアプリやクライアントを含む詳細については、「[条件付きアクセス アプリ制御を使用してアプリを保護Microsoft Defender for Cloud Apps」を](/cloud-app-security/proxy-intro-aad)参照してください。 

ポリシーの例については、「[SaaS アプリの推奨Microsoft Defender for Cloud Apps ポリシー」を](../office-365-security/mcas-saas-access-policies.md)参照してください。 これらのポリシーは、すべてのお客様の出発点として推奨される [一連の共通 ID およびデバイス アクセス ポリシー](../office-365-security/microsoft-365-policies-configurations.md) に基づいています。 

## <a name="step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment"></a>手順 3. 機能を試す - 環境を保護するためのチュートリアルについて説明します 

Microsoft Defender for Cloud Appsドキュメントには、リスクの検出と環境の保護に役立つ一連のチュートリアルが含まれています。 

Defender for Cloud Apps のチュートリアルを試す:

- [疑わしいユーザー アクティビティを検出する](/cloud-app-security/tutorial-suspicious-activity)
- [危険なユーザーを調査する](/cloud-app-security/tutorial-ueba)
- [危険な OAuth アプリを調査する](/cloud-app-security/investigate-risky-oauth)
- [機密情報を検出して保護する](/cloud-app-security/tutorial-dlp)
- [組織内のすべてのアプリをリアルタイムで保護する](/cloud-app-security/tutorial-proxy)
- [機密情報のダウンロードをブロックする](/cloud-app-security/use-case-proxy-block-session-aad)
- [管理者検疫を使用してファイルを保護する](/cloud-app-security/use-case-admin-quarantine)
- [危険なアクションに対してステップアップ認証を要求する](/cloud-app-security/tutorial-step-up-authentication)

Microsoft Defender for Cloud Apps データの高度な捜索の詳細については、[ビデオ](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)を参照してください。

## <a name="next-steps"></a>次の手順

[パイロット環境でMicrosoft 365 Defenderを使用して調査し、対応する](eval-defender-investigate-respond.md)

[Microsoft Defender for Cloud Appsの評価](eval-defender-mcas-overview.md)の概要に戻る

[評価とパイロットのMicrosoft 365 Defender](eval-overview.md)の概要に戻る
