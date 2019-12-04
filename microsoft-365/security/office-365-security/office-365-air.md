---
title: Office 365 の脅威を自動的に調査し対応する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/03/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動インシデント対応機能の使用を開始します。
ms.openlocfilehash: 9db3a788f5a2f2c7101b5165935884c1d76bccbd
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813867"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Office 365 の脅威を自動的に調査し対応する

## <a name="overview"></a>概要

サブスクリプションによっては、 [Office 365 Advanced Threat Protection](office-365-atp.md)には、セキュリティ運用チームの時間と、アラートと脅威を処理するための労力を節約できる自動化されたインシデント対応 (航空) 機能が含まれることがあります。

- Office 365 の AIR 機能の使用を開始するには、この記事をご利用ください。 
- 空気のしくみの概要については、「Office 2010 の[自動インシデント対応 (AIR) 365](automated-investigation-response-office.md)」を参照してください。

AIR を使用すると、特定のアラートがトリガーされ、1つ以上のセキュリティプレイブックが開始され、自動調査が開始します。 自動化された調査プロセスの最中および実行後に、管理者およびセキュリティ運用チームは次のことを行うことができます。

- [調査の詳細を表示する](#view-details-of-an-investigation)
- [調査の結果としてアクションを確認して承認する](#review-and-approve-actions) 
- [調査に関連する通知の詳細を表示する](#view-details-about-an-alert-related-to-an-investigation)

## <a name="view-details-of-an-investigation"></a>調査の詳細を表示する

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. 次のいずれかの操作を行います。

    - [**脅威管理** > ]**ダッシュボード**に移動します。 これにより、[セキュリティダッシュボード](security-dashboard.md)が表示されます。 エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。 **調査の概要**などのウィジェットを選択します。

    - [**脅威管理** > の**調査**] に移動します。 

    どちらの方法でも、調査の一覧を取得できます。

    ![AIR のメインの調査ページ](../media/air-maininvestigationpage.png) 

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 これにより、調査の詳細ページが開き、[調査] グラフが表示されます。

    ![ARI の [調査グラフ] ページ](../media/air-investigationgraphpage.png)

4. 調査の詳細については、さまざまなタブを使用してください。

## <a name="review-and-approve-actions"></a>アクションの確認と承認

Office 365 では、通常、自動調査は1つまたは複数の推奨されるアクションになります。 ただし、セキュリティ運用チームによって承認されるまで、アクションは実行されません。 アクションを確認して承認するには、以下の手順を使用します。

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 

2. [**脅威管理** > の**調査**] に移動します。

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 

3. 調査の詳細ビューで、[**操作**] タブを選択します。承認待ちのすべてのアクションがここに表示されます。

4. リストからアイテムを選択します。

5. 推奨されるアクションを実行する場合は [**承認**] を選択します (アクションを行わずに調査を終了する場合は**拒否**)。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>調査に関連する通知の詳細を表示する

特定の種類の通知では、Office 365 で自動調査がトリガーされます。 詳細については、「 [Alerts](automated-investigation-response-office.md#alerts)」を参照してください。 次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. [**脅威管理** > の**調査**] に移動します。

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 

4. 調査の詳細を開いた状態で、[**通知**] タブを選択します。調査をトリガーしたアラートが一覧表示されています。

5. リストからアイテムを選択します。 ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。

6. ポップアップの情報を確認し、特定の通知に応じて、ユーザーの**解決**、**抑制**、または**通知**などのアクションを実行します。 

    - **解決**は通知を閉じることと同じです。
    
    - **抑制**すると、指定した期間、ポリシーがアラートをトリガーしなくなります。
    
    - **通知**ユーザーに既に入力されたユーザーのメールアドレスを使用してメールを開始し、セキュリティ運用チームがそれらのユーザーにメッセージを入力できるようにします。 (これは、[脅威エクスプローラー](threat-explorer.md)を使用してメッセージを受信者に送信するのと似ています。)  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する

組織でカスタムまたはサードパーティのレポートソリューションを使用している場合は、Office 365 Management Activity API を使用して、そのソリューションの自動化された調査に関する情報を表示できます。

これを設定するには、次のリソースを使用します。

|Resource  |説明  |
|---------|---------|
|[Office 365 管理 API の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。         |
|[Office 365 管理 API の使用を開始する](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。 これを設定するには、この記事の手順に従います。          |
|[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。 この機能の詳細については、この記事を参照してください。        |
|[Office 365 管理アクティビティ API のスキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。         |

## <a name="next-steps"></a>次の手順

- [空気を取得し、必要なアクセス許可を確認する方法を確認する](automated-investigation-response-office.md#how-to-get-air)
- [通知の詳細情報](../../compliance/alert-policies.md)
- [Office 365 で配信された悪意のある電子メールを手動で検索して調査する](investigate-malicious-email-that-was-delivered.md)
- [Microsoft Defender ATP の AIR についての詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する](https://www.microsoft.com/microsoft-365/roadmap?filters=)