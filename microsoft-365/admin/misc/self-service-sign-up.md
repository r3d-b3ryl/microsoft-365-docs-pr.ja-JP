---
title: 組織でのセルフサービス サインアップの使用
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_signup
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
description: microsoft Power Apps、Microsoft Power Automate、Dynamics 365 for Finance などのMicrosoft 365セルフサービス サインアップと利用可能なセルフサービス プログラムについて説明します。
ms.date: 03/17/2021
ms.openlocfilehash: 67f0955a4485ea0f668b143f485b34cf2935404b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319859"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>組織でのセルフサービス サインアップの使用

セルフサービス サインアップを使用すると、組織内のユーザーが Microsoft からオンライン サービスにサインアップしやすくなります。 このサインアップ プロセスを "セルフサービス サインアップ" と呼びます。これは、ユーザーがサブスクリプションによって支払われたサービスを使用するためにサインアップしたり、無料のサービスを使用したりできるため、ユーザーに代わってアクションを実行するように求めないためです。

## <a name="how-self-service-sign-up-works"></a>セルフサービス サインアップのしくみ

次の例は、学校の場合のセルフサービス サインアップのしくみを説明しています。テナントでセルフサービス プログラムを有効にしているどの組織の場合も、同じプロセスを使用できます。

1. 学生と教職員は、自らが学校に関連付けられていることを示す、学校のメール アドレスを持ちます。 たとえば、jakob@uw.edu メール アドレスは、ワシントン大学の学生を示している場合があります。
2. 学生と教職員は[、Web サイト](https://go.microsoft.com/fwlink/p/?LinkId=536628)にアクセスし、電子メール アドレスを使用して、組織が提供するサービス (Microsoft 365 Apps for enterpriseなど) にサインアップします。 学生と教職員は、Microsoft が提供する他の無料サービスにサインアップすることもできます。
3. メール アドレスを検証すると、すぐにMicrosoft 365、Power BI、またはその他のサービスの使用を開始できます。
4. ビジネス管理者は、Microsoft 365 管理センターの **[ライセンス**] ページでサブスクリプションを選択することで、サブスクリプションにサインアップしたユーザーを確認できます。 これにより、テナント内のサービスに対して新しいライセンスまたは認識されないライセンスがある場合を確認できます。 ユーザーがセルフサービス サブスクリプションにサインアップできるかどうかを制御するには、**AllowAdHocSubscriptions** パラメーターを使用して [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell コマンドレットを使用します。 詳細については、「[セルフサービス設定操作方法制御](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)する」を参照してください。

## <a name="available-self-service-programs"></a>利用可能なセルフサービス プログラム

以下は、現在利用可能なセルフサービス プログラムです。この一覧は、新しいプログラムが追加されるたびに更新されます。

| プログラム <br/> | 説明 <br/> | 追加情報 <br/> | セルフサービスサインアップ用の Web サイト <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |任意の学生または教師は、学校の電子メール アドレスを使用して無料のOffice 365にサインアップし、web 用のOffice アプリ、1 TB の OneDriveクラウド ストレージ、SharePoint Online (クラス、チーム、プロジェクト サイト用) を取得できます。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |対象となる学生と教師は、上記のすべてとMicrosoft 365 Apps for enterpriseを含むOffice 365 A1 Plus にサインアップできます。 Microsoft 365 Apps for enterpriseは、Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access、Skype for Businessなどの生産性ソフトウェアです。は、デスクトップコンピューターまたはノート PC にインストールされます。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BIを使用すると、ユーザーは直感的な新しい方法でデータの視覚化、検出の共有、共同作業を行うことができます。 <br/> 組織が既にサブスクライブしている場合は、"Power BI Pro個別ユーザー試用版" のライセンスが追加で表示される場合があります。これにより、ユーザーは高度な機能に無料でアクセスできます。  <br/> |[組織内の Power BI](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS (Rights Management Services)** <br/> |個人用の RMS は、Azure Rights Management (Azure RMS) で保護された機密性の高いファイルが送信されているが、IT 部門が Azure Rights Management (Azure RMS)、Active Directory Rights Management Services (AD RMS) のいずれも実装していない組織に所属するユーザーのための無料のセルフサービス サブスクリプションです。  <br/> |[個人用の RMS と Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management ポータル](https://portal.azure.com/) したがって、お客様は、特定の権利保護されたドキュメントを開くことができるかどうかをチェックできます。  <br/> |
|**Microsoft Power Apps** <br/> |Power Appsでは、自分が作成したアプリ、または他のユーザーが作成して共有したアプリを実行して、組織データを管理できます。 アプリは携帯電話などのモバイル デバイスで実行するか、Dynamics 365 を開いてブラウザーで実行できます。 C# などのプログラミング言語を学習することなく、無限のさまざまなアプリを作成できます。  <br/> |[Power Appsのセルフサービス サインアップ](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |中小企業向けの完全なビジネス ソリューションおよび財務管理ソリューションを提供します。Dynamics 365 for Financials を使用することで、使用開始の 1 日目から注文、販売、請求書やレポートの作成が容易になります。  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |ビジネスのスピードを加速できます。Dynamics 365 for Operations の完全な ERP ツールは、グローバルなスケーラビリティとデジタル インテリジェンスを提供し、企業のペースに応じた成長をサポートします。  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource は、Microsoft クラウド プラットフォーム上に構築された SaaS (サービスとしてのソフトウェア) のビジネス アプリを対象としています。 AppSource には、Azure、Dynamics 365、Office 365、Power BIなどの Microsoft 製品の機能を拡張する何百ものアプリ、アドオン、コンテンツ パックが用意されています。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft パートナー インセンティブ** <br/> |Microsoft パートナー ネットワークでは、3 種類のメンバーシップを提供しています。各メンバーシップでは、ビジネスの成長をサポートするさまざまな特典をご用意しています。目標の実現に向けて、お客様の固有のニーズに合ったレベルのプログラムにご参加いただき、より多くの特典を得て、Microsoft やネットワーク内のその他のパートナーとの関係を深めてください。  <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center は、Microsoft 製品およびサービス契約 (MPSA) を通じて購入したお客様向けのポータルです。 <br/> |[クイック スタート: Microsoft Business Center への登録](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |Microsoft Volume License Service Center には、Enterprise、選択、教育機関 (キャンパスまたは学校)、Open Value、Open License、ISV のロイヤリティ契約で購入したライセンスが表示されます。  <br/> |[VLSC トレーニングとリソース](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |学習目的のプラットフォームとして Minecraft を使用することで、教師は各学生のモチベーションやインスピレーションを奮起させ、学習意欲を高めることができます。教師コミュニティに参加して、Minecraft の使用方法を学び、学生の潜在能力を開花させてください。  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |組織全体でビデオをアップロードおよび共有して、コミュニケーション力、共同作業、学習の向上を実現します。  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automateは、ファイルの同期、通知の取得、データの収集などを行うために、お気に入りのアプリとサービスの間で自動化されたワークフローを設定するのに役立つ製品です。  <br/> |[Power Automateにサインアップしてサインインする](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agentsでは、データ サイエンティストや開発者を必要とせずに、ガイド付きのコードなしのグラフィカル インターフェイスを使用して強力なボットを簡単に作成できます。 Power Virtual Agentsは、今日の業界におけるボットの構築に関する主要な問題の多くに対処しています。 これにより、問題の専門家とボットを構築する開発チーム間のギャップと、問題を認識し、それに対処するためにボットを更新するチーム間の長い待ち時間が解消されます。  <br/> |[ライセンスとアクセスの詳細](/power-virtual-agents/requirements-licensing) <br/> |[Power Virtual Agentsにサインアップする](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) の企業間 (B2B) コラボレーションを使用すると、外部ユーザー (または "ゲスト ユーザー") を招待して有料Azure AD サービスを使用できます。 一部の機能は無料ですが、有料のAzure AD機能では、従業員またはテナント内の非ゲスト ユーザーに対して所有するAzure ADエディションライセンスごとに最大 5 人のゲスト ユーザーを招待できます。 <br/> |[Azure AD B2B コラボレーションサインアップのセルフサービス](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B コラボレーション ライセンスガイダンス](/azure/active-directory/b2b/licensing-guidance) <br/> |
