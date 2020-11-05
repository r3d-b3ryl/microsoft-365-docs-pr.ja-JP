---
title: Office 2007 または2010のサーバーとクライアントからのアップグレードを計画する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: b2acaeca-4986-40f4-92b7-a1bdd06e549d
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事には、Office 2007 または Office 2010 を使用してアップグレードを計画するユーザー向けのリソースが含まれています。
ms.openlocfilehash: 4fa340f2dfa8091aba962da475f5ffb883ba4e3f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920269"
---
# <a name="plan-your-upgrade-from-office-2007-or-office-2010-servers-and-clients"></a>Office 2007 または Office 2010 サーバー/クライアントからアップグレードする計画を立てる

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

以前のバージョンの Office 製品とサーバーを使用している組織では、アップグレードの計画を開始する絶好の時間です。 Office 2007 製品とサービス [のサポートが終了](upgrade-from-office-2007-servers-and-products.md)しました。 Office 2010 製品およびサービスの場合:

- Office 2010 と Exchange 2010 *が2020年10月 13* 日にサポート終了に達しました。 
- SharePoint 2010 および Project Server 2010 は、 *2021年4月13日* にサポートが終了します。 

詳細については、「 [Upgrade From Office 2010 servers and clients](upgrade-from-office-2010-servers-and-products.md)」を参照してください。

この記事のリソースを使用して、アップグレードを開始します。

## <a name="what-is-microsoft-365"></a>Microsoft 365 とは

[Microsoft 365](https://www.microsoft.com/microsoft-365) は、より多くのことを実現するために設計された革新的な Office アプリ、インテリジェントクラウドサービス、および世界最高クラスのセキュリティの組み合わせです。

Microsoft 365 には、組織が最新の Windows オペレーティングシステムで動作していることを確認するためのライセンスと機能が含まれています。 また、Windows、iOS、および Android デバイスが、認証とデータ保護を必要とするポリシーによって確実に登録され、セキュリティで保護されます。 さらに、Windows 10 および Microsoft 365 Apps for enterprise (旧称 Office 365 ProPlus) クライアントソフトウェアは、最新の機能とセキュリティ更新プログラムが含まれるように、継続的に更新されています。
  
Microsoft 365 は、Microsoft クラウドによって有効になっていてセキュリティで保護されたデバイスと生産性のエクスペリエンスを常に向上させて、ビジネスをデジタル的に変換する方法です。
 
|関連情報|説明|
|---|---|
|[Microsoft 365](https://www.microsoft.com/microsoft-365)|Microsoft 365 のバージョンに関する情報を取得します。|
|[Microsoft 365 Business ドキュメント](https://docs.microsoft.com/microsoft-365/business/)|小規模および中規模企業向けの Microsoft 365 のバージョンに関する詳細情報を取得します。|
|[Microsoft 365 教育に関するドキュメント](https://docs.microsoft.com/microsoft-365/education/)|教育機関向けの Microsoft 365 のバージョンに関する詳細情報を取得します。|
|[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365/enterprise/)|エンタープライズ組織の Microsoft 365 のバージョンに関する詳細情報を取得します。|
|||

## <a name="what-happens-if-i-dont-upgrade"></a>アップグレードしない場合はどうなりますか?

現時点では、アップグレードしないことを選択できます。 オンプレミスのサーバーおよびアプリケーションは引き続き実行されます。 しかし、セキュリティ更新プログラムまたはサポートオプションを受信できなくなった場合、組織はセキュリティ侵害に対して脆弱になる可能性があります。 アップグレードをすぐに計画することを強くお勧めします。 Microsoft 365 またはオンプレミスのサーバーおよびアプリケーションの新しいバージョンにアップグレードできます。

## <a name="what-upgrade-options-are-available"></a>利用可能なアップグレードオプションを教えてください。      

組織は、いくつかのアップグレードオプションを考慮する必要があります。

- **オンプレミスのサーバーとアプリケーションをアップグレードします。** オンプレミスの Office 製品とサーバーアプリケーションを使用している場合は、次の計画コンテンツを参照してください。<br/> 

  |Office 2007 の製品とサービス|Office 2010 の製品とサービス|
  |---|---|
  |[Office 2007](https://docs.microsoft.com/DeployOffice/office-2007-end-support-roadmap) (デスクトップ)|[Office 2010](https://docs.microsoft.com/DeployOffice/office-2010-end-support-roadmap) (デスクトップ)|
  |[Exchange 2007](exchange-2007-end-of-support.md)|[Exchange 2010](exchange-2010-end-of-support.md)|
  |[SharePoint 2007](sharepoint-2007-end-of-support.md)|[SharePoint 2010](upgrade-from-sharepoint-2010.md)|
  |[Office Communications Server](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)|[Lync Server 2010](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)|
  |[Project Server 2007](project-server-2007-end-of-support.md)|[Project Server 2010](project-server-2010-end-of-support.md)|
  |[PerformancePoint Server 2007](pps-2007-end-of-support.md)||
 
- **Microsoft 365 または Office 365 を使用してハイブリッドソリューションを実装します。** ハイブリッドソリューションでは、オンプレミスのサーバーとアプリケーション、およびそのクラウドに相当するものを使用します。 段階的にクラウドに移行する場合や、一部のサーバーとアプリケーションをオンプレミスのままにしておく必要がある場合は、ハイブリッドソリューションが組織に適している場合があります。 詳細については、「 [Microsoft cloud architecture モデル](../solutions/cloud-architecture-models.md)」を参照してください。 
    
- **Microsoft 365 または Office 365 を使用してクラウドに移行します。** 多くのお客様にとって、クラウドに移行することは、効率的で費用効果の高いソリューションです。 クラウドへの完全な移行により、セットアップと継続的な管理が容易になります。 このオプションは、最新の機能およびセキュリティ更新プログラムをシームレスに提供します。 詳細については、この記事の「 [Microsoft 365](#what-is-microsoft-365) について」を参照してください。
    
## <a name="can-i-get-help-for-my-organization"></a>組織のヘルプを取得できますか?

アップグレードの計画については、次の1つ以上のオプションを検討してください。

- パートナーまたはボリュームライセンスの専門家と協力します。 [Microsoft 365 パートナーまたは販売店を検索](https://support.office.com/article/b6c18a9b-2aed-4c84-9d75-af709160258c.aspx)します。 

- 組織が正規の数の Microsoft 365 ライセンスを購入した場合、FastTrack チームはセットアッププロセスを支援することができます。 詳細については、「 [Microsoft 365 の Fasttrack](https://www.microsoft.com/fasttrack/microsoft-365)」を参照してください。

- 小規模な組織に属している場合、または組織の Office アップグレードを自分で処理する場合は、「 [Microsoft 365 Business ユーザーを最新の office クライアントにアップグレードする](https://docs.microsoft.com/office365/admin/setup/upgrade-users-to-latest-office-client)」を参照してください。 
  
## <a name="im-a-home-user-what-do-i-do"></a>私はホーム ユーザーです。 どうしたらよいでしょうか。

Office 2007 または Office 2010 を自宅で使用している場合は、次のアップグレードオプションを検討してください。

- **無料のブラウザーで Office を使用します。** ブラウザーで Office ファイルを作成、表示、編集します。 インターネットにアクセスできるすべてのデバイスから、これらのファイルへのアクセスを取得します。 

  [Web 上の Office に](https://products.office.com/office-online/documents-spreadsheets-presentations-office-online) は、 [Web](https://go.microsoft.com/fwlink/p/?linkid=746664)用の Word、web 用の [Excel](https://go.microsoft.com/fwlink/p/?linkid=746665)、web 用の [PowerPoint](https://go.microsoft.com/fwlink/p/?linkid=746666)、web 用の [OneNote](https://go.microsoft.com/fwlink/p/?linkid=746674)、 [Sway](https://go.microsoft.com/fwlink/p/?linkid=746675)、 [電子メール](https://go.microsoft.com/fwlink/p/?linkid=746676)、 [予定表](https://go.microsoft.com/fwlink/p/?linkid=746678)、および [OneDrive](https://go.microsoft.com/fwlink/p/?linkid=746679)が含まれています。 開始するには、 [Office.com](https://office.com) にアクセスし、 [Microsoft アカウント](https://account.microsoft.com/account)を使用してサインインします。 Microsoft アカウントをお持ちでない場合は、 [Office.com](https://office.com)で作成できます。

- **Microsoft 365 ファミリをお試しください。** [Microsoft 365 ファミリ](https://www.microsoft.com/microsoft-365/p/microsoft-365-family/cfq7ttc0k5dm?rtc=2&activetab=pivot:overviewtab)の試用版を開始して、ユーザーがどのように機能するかを確認します。 Microsoft 365 ファミリでは、クラウドストレージを OneDrive で利用できます。

  Windows 7 のサポートは [、2020年1月14日に終了しまし](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)た。 Office 365 のホームまたは Office 365 Personal で提供される Word、Excel、PowerPoint、Outlook、Publisher、および Access のバージョンには、セキュリティ更新プログラムは提供されますが、機能更新プログラムはありません。 これらのアプリケーションの機能更新プログラムの受信を続行するには、 [windows 7 デバイスを windows 10 にアップグレード](https://support.microsoft.com/help/12435/windows-10-upgrade-faq)します。
    
- **Office Home &amp; の学生を購入します。** このオプションを選択する場合は、1回限りの購入を行い、Windows PC または Mac に Office をインストールします。 この購入はサブスクリプションではありません。1台のコンピューターでは、1回限りの永続的な使用ライセンスとなります。 [要件](https://office.com/systemrequirements)を確認し、バージョンを選択します。

  - Windows 10 を実行している Windows PC では、 [Office Home & Student 2019](https://www.microsoft.com/p/office-home-student-2019/cfq7ttc0k7c8)を入手することを検討してください。

  - Windows 7、8、または8.1 を実行していて、windows 10 にアップグレードしていない場合は、Office Home & Student 2016 または Microsoft Office の他のエディションを入手することを検討してください。 承認された販売店から入手できます。
     
    Windows 7 のサポートは [、2020年1月14日に終了しまし](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)た。 Microsoft は、セキュリティ更新プログラムを提供しなくなりました。 継続的なセキュリティおよび機能の更新プログラムおよび継続的なサポートを行うために、Windows 7 デバイスを Windows 10 にアップグレードします。

今アップグレードしないことを選択すると、Office アプリは [タイムライン](https://support.microsoft.com/lifecycle/search/13615)に従って引き続き実行されます。 ただし、セキュリティ更新プログラムまたは新機能と強化された機能を取得するには、アップグレードする必要があります。
   
## <a name="next-steps"></a>次の手順

- [Office 2007 サーバー/クライアントからアップグレードする](upgrade-from-office-2007-servers-and-products.md)
- [Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
   
## <a name="related-topics"></a>関連項目
  
[Microsoft のライフサイクル ポリシー](https://go.microsoft.com/fwlink/?linkid=865200)
