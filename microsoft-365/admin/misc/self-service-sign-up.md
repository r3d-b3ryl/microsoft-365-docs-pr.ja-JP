---
title: 組織でのセルフサービス サインアップの使用
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Microsoft Microsoft 365、Microsoft Power Apps、Microsoft Power Automate、Dynamics 365 for Finance などのセルフサービス プログラムについて説明します。
ms.date: 03/17/2021
ms.openlocfilehash: 7c4986beb1c920865cee28f2729859e426944f3f
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58532789"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>組織でのセルフサービス サインアップの使用

セルフサービス サインアップを使用すると、組織内のユーザーが Microsoft からのオンライン サービスにサインアップしやすくなります。 このサインアップ プロセスを "セルフサービス サインアップ" と呼ぶのは、ユーザーがサブスクリプションによって支払われたサービスを使用するためにサインアップしたり、無料のサービスを使用したりすることができるため、ユーザーに代わってアクションを実行する必要はありません。

## <a name="how-self-service-sign-up-works"></a>セルフサービスサインアップの仕組み

次の例は、学校の場合のセルフサービス サインアップのしくみを説明しています。テナントでセルフサービス プログラムを有効にしているどの組織の場合も、同じプロセスを使用できます。

1. 学生と教職員は、自らが学校に関連付けられていることを示す、学校のメール アドレスを持ちます。 たとえば、電子メール アドレス jakob@uw.edu ワシントン大学の学生を示している場合があります。
2. 学生と教職員は、Web サイトに移動し、その電子メール アドレスを使用して、組織が提供するサービスにサインアップMicrosoft 365 Apps for enterprise。 [](https://go.microsoft.com/fwlink/p/?LinkId=536628) 学生と教職員は、Microsoft が提供する他の無料サービスにサインアップすることもできます。
3. メール アドレスを検証し、その後、Microsoft 365、Power BI、または他のサービスの使用を開始できます。
4. ビジネス管理者は、サブスクリプションにサインアップしたユーザーを確認するには、サブスクリプションの [ライセンス] ページでサブスクリプションを選択Microsoft 365 管理センター。 この方法では、テナント内のサービスの新しいライセンスまたは認識されていないライセンスがある場合を確認できます。 ユーザーがセルフサービス サブスクリプションにサインアップできるかどうかを制御するには **、AllowAdHocSubscriptions** パラメーターを使用して [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell コマンドレットを使用します。 詳細については、「セルフサービス設定 [を制御する方法」を参照してください。](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>利用可能なセルフサービス プログラム

以下は、現在利用可能なセルフサービス プログラムです。この一覧は、新しいプログラムが追加されるたびに更新されます。

| プログラム <br/> | 説明 <br/> | 追加情報 <br/> | セルフサービス サインアップ用の Web サイト <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |学生または教師は、学校の電子メール アドレスを使用して無料の Office 365 にサインアップし、Office アプリを web 用に取得し、OneDrive クラウド ストレージを 1 TB、クラス、チーム、プロジェクト サイト用に SharePoint Online を取得できます。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1Plus** <br/> |対象となる学生と教師は、上記のOffice 365 A1と他のユーザーを含む、Office 365 A1 Plus にサインアップMicrosoft 365 Apps for enterprise。 Microsoft 365 Apps for enterpriseは、デスクトップまたはラップトップ コンピューターにインストールされている Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access、Skype for Business などの生産性ソフトウェアです。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BIユーザーは、直感的な新しい方法でデータの視覚化、発見の共有、共同作業を行うことができます。 <br/> 組織が既に購読している場合は、ユーザーに制限された高度な機能への無料アクセスを提供する「Power BI Pro 個人ユーザー試用版」のライセンスが追加で表示される場合があります。  <br/> |[組織内の Power BI](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS (Rights Management Services)** <br/> |個人用の RMS は、Azure Rights Management (Azure RMS) で保護された機密性の高いファイルが送信されているが、IT 部門が Azure Rights Management (Azure RMS)、Active Directory Rights Management Services (AD RMS) のいずれも実装していない組織に所属するユーザーのための無料のセルフサービス サブスクリプションです。  <br/> |[個人用の RMS と Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management ポータル](https://portal.azure.com/) したがって、お客様は、特定の権利保護されたドキュメントを開くことができるかどうかをチェックできます。  <br/> |
|**Microsoft Power Apps** <br/> |このPower Apps、作成したアプリ、または他のユーザーが作成して共有したアプリを実行して、組織データを管理できます。 アプリは携帯電話などのモバイル デバイスで実行するか、Dynamics 365 を開いてブラウザーで実行できます。 アプリケーションなどのプログラミング言語を学習せずに、無限に多様なアプリを作成C#。  <br/> |[セルフサービスのアカウントにサインアップPower Apps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |中小企業向けの完全なビジネス ソリューションおよび財務管理ソリューションを提供します。Dynamics 365 for Financials を使用することで、使用開始の 1 日目から注文、販売、請求書やレポートの作成が容易になります。  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |ビジネスのスピードを加速できます。Dynamics 365 for Operations の完全な ERP ツールは、グローバルなスケーラビリティとデジタル インテリジェンスを提供し、企業のペースに応じた成長をサポートします。  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource は、Microsoft クラウド プラットフォーム上に構築された SaaS (サービスとしてのソフトウェア) のビジネス アプリを対象としています。 AppSource には、Azure、Dynamics 365、Office 365、Power BI など、Microsoft 製品の機能を拡張する何百ものアプリ、アドオン、およびコンテンツ パックが備Power BI。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft パートナー インセンティブ** <br/> |Microsoft パートナー ネットワークでは、3 種類のメンバーシップを提供しています。各メンバーシップでは、ビジネスの成長をサポートするさまざまな特典をご用意しています。目標の実現に向けて、お客様の固有のニーズに合ったレベルのプログラムにご参加いただき、より多くの特典を得て、Microsoft やネットワーク内のその他のパートナーとの関係を深めてください。  <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center は、Microsoft 製品とサービス契約 (MPSA) を通じて購入したお客様向けポータルです。 <br/> |[クイック スタート: Microsoft Business Center への登録](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft ボリューム ライセンス サービス センター** <br/> |Microsoft ボリューム ライセンス サービス センターには、Enterprise、Select、Education (キャンパスまたは学校)、オープンバリュー、オープン ライセンス、ISV ロイヤルティ契約で購入したライセンスが表示されます。  <br/> |[VLSC のトレーニングとリソース](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |学習目的のプラットフォームとして Minecraft を使用することで、教師は各学生のモチベーションやインスピレーションを奮起させ、学習意欲を高めることができます。教師コミュニティに参加して、Minecraft の使用方法を学び、学生の潜在能力を開花させてください。  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |組織全体でビデオをアップロードおよび共有して、コミュニケーション力、共同作業、学習の向上を実現します。  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automateは、ファイルの同期、通知の取得、データの収集など、お気に入りのアプリとサービスの間で自動化されたワークフローをセットアップするのに役立つ製品です。  <br/> |[サインアップしてサインインして、Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agentsチームは、データ サイエンティストや開発者を必要とせずに、ガイド付きのコードなしのグラフィカル インターフェイスを使用して強力なボットを簡単に作成できます。 Power Virtual Agents業界におけるボットの構築に関する主な問題の多くに取り組む必要があります。 これは、問題の専門家と開発チームがボットを構築する間のギャップを排除し、問題を認識し、ボットを更新して対処するチーム間の長い待機時間を排除します。  <br/> |[ライセンスとアクセスの詳細](/power-virtual-agents/requirements-licensing) <br/> |[アカウントにサインアップPower Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) の企業間 (B2B) コラボレーションを使用すると、外部ユーザー (または "ゲスト ユーザー") を招待して有料の Azure AD サービスを使用できます。 一部の機能は無料ですが、有料の Azure AD 機能では、従業員またはテナント内のゲスト以外のユーザーに所有する Azure AD エディションライセンスごとに最大 5 人のゲスト ユーザーを招待できます。 <br/> |[Azure AD B2B コラボレーション サインアップのセルフサービス](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active DirectoryB2B コラボレーション ライセンスのガイダンス](/azure/active-directory/b2b/licensing-guidance) <br/> |
