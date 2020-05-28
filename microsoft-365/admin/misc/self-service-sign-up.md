---
title: 組織でのセルフサービス サインアップの使用
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Microsoft 365 セルフサービスのサインアップと、Microsoft パワーアプリ、Microsoft Flow、および財務の Dynamics 365 などの利用可能なセルフサービスプログラムについて説明します。
ms.openlocfilehash: d2d4d23eeb3ddeda0dc5b66acfe072a66f4ce267
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399292"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>組織でのセルフサービス サインアップの使用

ご意見ご感想をお待ちしており、組織内のユーザーが Microsoft からオンラインサービスにサインアップすることが容易になりました。 この新しいサインアップ処理では、ユーザーはサブスクリプションによって支払われるサービスを使用するようにサインアップすることができます。または、自分に代わってアクションを実行することを求められずに、無料のサービスを使用することができます。
  
## <a name="how-self-service-sign-up-works"></a>セルフサービス サインアップのしくみ

次の例は、学校の場合のセルフサービス サインアップのしくみを説明しています。テナントでセルフサービス プログラムを有効にしているどの組織の場合も、同じプロセスを使用できます。
  
1. 学生と教職員は、自らが学校に関連付けられていることを示す、学校のメール アドレスを持ちます。たとえば、メール アドレス jakob@uw.edu はワシントン大学の学生であることを示します。

2. 学生と教職員は、[当社の web サイト](https://go.microsoft.com/fwlink/p/?LinkId=536628)に移動し、自分のメールアドレスを使用して、組織が提供する、企業向けの Microsoft 365 アプリなどのサービスにサインアップします。 学生と教職員は、Microsoft が提供する他の無料サービスにサインアップすることもできます。

3. 電子メールアドレスを検証し、Microsoft 365、Power BI、またはその他のサービスをすぐに使用できるようにします。

4. ビジネス管理者は、管理センターで [**製品**] ページを表示することによって、サブスクリプションにサインアップしたユーザーを確認できます。 このようにすると、テナント内のサービスのライセンスが新規にあるか、認識されないかを確認できます。 ユーザーがセルフサービスサブスクリプションにサインアップできるかどうかを制御するには、 [Set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell コマンドレットを**AllowAdHocSubscriptions**パラメーターと共に使用します。 詳細については、「[セルフサービス設定を制御する方法](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)」を参照してください。

## <a name="available-self-service-programs"></a>利用可能なセルフサービス プログラム

以下は、現在利用可能なセルフサービス プログラムです。この一覧は、新しいプログラムが追加されるたびに更新されます。
  
|||||
|:-----|:-----|:-----|:-----|
|**プログラム** <br/> |**説明** <br/> |**追加情報** <br/> |****セルフサービス サインアップ用の Web サイト**** <br/> |
|Office 365 A1 * * * * <br/> |任意の学生または教師は、学校の電子メールアドレスを使用して無料の Office 365 にサインアップし、web 用に Office アプリを入手できます。また、1 TB の OneDrive クラウドストレージと SharePoint Online を、クラス、チーム、およびプロジェクトサイトで利用できます。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |対象とする学生と教師は、Office 365 A1 Plus にサインアップできます。これには、上記のすべての機能と Microsoft 365 Apps for enterprise が含まれます。 Microsoft 365 enterprise 用アプリは、デスクトップまたはラップトップコンピューターにインストールされている Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access、Skype for Business などの生産性向上ソフトウェアです。  <br/> |[Office 365 Education についてよく寄せられる技術的な質問](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI を使用すると、ユーザーはデータを表示したり、探索を共有したり、直観的な新しい方法で共同作業したりできます。 <br/> 組織が既に加入している場合は、「Power BI Pro ユーザーの試用版」のライセンスが追加されている可能性があります。これは、ユーザーが限定的で、高度な機能へのアクセスを無料で提供しています。  <br/> |[組織内の Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS (Rights Management Services)** <br/> |個人用の RMS は、Azure Rights Management (Azure RMS) で保護された機密性の高いファイルが送信されているが、IT 部門が Azure Rights Management (Azure RMS)、Active Directory Rights Management Services (AD RMS) のいずれも実装していない組織に所属するユーザーのための無料のセルフサービス サブスクリプションです。  <br/> |[個人用の RMS と Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management ポータル](https://portal.azure.com/) したがって、お客様は、特定の権利保護されたドキュメントを開くことができるかどうかをチェックできます。  <br/> |
|**Microsoft Power Apps** <br/> |PowerApps では、管理者が作成したアプリ、または他のユーザーが作成して共有したアプリを実行することで組織データを管理することができます。アプリはスマートフォンなどのモバイル デバイスで動作します。または Dynamics 365 を開くことによって、ブラウザで実行することもできます。無限の多様性を備えるアプリを作成することができます。すべて、C# などのプログラミング言語は必要ありません。  <br/> |[PowerApps のセルフサービス サインアップ](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |中小企業向けの完全なビジネス ソリューションおよび財務管理ソリューションを提供します。Dynamics 365 for Financials を使用することで、使用開始の 1 日目から注文、販売、請求書やレポートの作成が容易になります。  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |ビジネスのスピードを加速できます。Dynamics 365 for Operations の完全な ERP ツールは、グローバルなスケーラビリティとデジタル インテリジェンスを提供し、企業のペースに応じた成長をサポートします。  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource は、Microsoft クラウド プラットフォーム上に構築された SaaS (サービスとしてのソフトウェア) のビジネス アプリを対象としています。AppSource では、Azure、Dynamics 365、Office 365、Power BI などの Microsoft 製品の機能を拡張する数百のアプリ、アドオン、コンテンツ パックを扱っています。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft パートナー インセンティブ** <br/> |Microsoft パートナー ネットワークでは、3 種類のメンバーシップを提供しています。各メンバーシップでは、ビジネスの成長をサポートするさまざまな特典をご用意しています。目標の実現に向けて、お客様の固有のニーズに合ったレベルのプログラムにご参加いただき、より多くの特典を得て、Microsoft やネットワーク内のその他のパートナーとの関係を深めてください。  <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft パートナー インセンティブ](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft ビジネスセンターは、Microsoft 製品とサービス契約 (MPSA) を通じて購入したお客様のためのポータルです。 <br/> |[クイック スタート: Microsoft Business Center への登録](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft ボリュームライセンスサービスセンター** <br/> |Microsoft ボリュームライセンスサービスセンターには、Enterprise で購入したライセンス、選択、教育 (キャンパスまたは学校)、オープン価値、オープンライセンス、ISV ロイヤリティアグリーメントが表示されます。  <br/> |[VLSC のトレーニングとリソース](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[ボリュームライセンスサービスセンター](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |学習目的のプラットフォームとして Minecraft を使用することで、教師は各学生のモチベーションやインスピレーションを奮起させ、学習意欲を高めることができます。教師コミュニティに参加して、Minecraft の使用方法を学び、学生の潜在能力を開花させてください。  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |組織全体でビデオをアップロードおよび共有して、コミュニケーション力、共同作業、学習の向上を実現します。  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power オートメーションは、ファイルを同期したり、通知を取得したり、データを収集したりするための、お気に入りのアプリとサービス間の自動化されたワークフローを設定するのに役立つ製品です。  <br/> |[電源自動化のためのサインアップとサインイン](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |パワー仮想エージェントは、データ科学者や開発者を必要とせずに、ガイド付きのコーディングされていないグラフィカルインターフェイスを使用して、チームが強力なボットを簡単に作成できるようにします。 パワー仮想エージェントは、現在業界での bot が構築する主な問題の多くを解決します。 該当分野の専門家と bot を構築する開発チームのギャップを排除し、teams を認識し、チーム間で問題を認識して、それに対処するために bot の待機時間を長くします。  <br/> |[ライセンスとアクセスの詳細](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[パワー仮想エージェントにサインアップする](https://aka.ms/TryPVA) <br/> |