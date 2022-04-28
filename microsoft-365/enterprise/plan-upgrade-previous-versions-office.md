---
title: Office 2007 または 2010 サーバーとクライアントからのアップグレードを計画する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: b2acaeca-4986-40f4-92b7-a1bdd06e549d
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事には、Office 2007 または 2010 Officeを使用するユーザーのアップグレード計画に役立つリソースが含まれています。
ms.openlocfilehash: ba57eb9f6f1b3c0d573b19b63da1fdd2c1a2b879
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100261"
---
# <a name="plan-your-upgrade-from-office-2007-or-office-2010-servers-and-clients"></a>Office 2007 または Office 2010 サーバー/クライアントからアップグレードする計画を立てる

*この記事は、EnterpriseのEnterpriseとOffice 365の両方のMicrosoft 365に適用されます。*

組織で古いバージョンのOffice製品とサーバーを使用している場合は、アップグレードの計画を開始するのに最適な時期になりました。 Office 2007 の製品とサービスが[サポート終了に](upgrade-from-office-2007-servers-and-products.md)達しました。 Office 2010 製品とサービスの場合:

- 2010 年と 2010 年Exchange Office、*2020 年 10 月 13* 日にサポートが終了しました。 
- SharePoint 2010 および Project Server 2010 は、*2021年4月13日* にサポートが終了します。 

詳細については、「[Office 2010 サーバーとクライアントからのアップグレード](upgrade-from-office-2010-servers-and-products.md)」を参照してください。

この記事のリソースを使用して、アップグレードを開始します。

## <a name="what-is-microsoft-365"></a>Microsoft 365とは

[Microsoft 365](https://www.microsoft.com/microsoft-365)は、革新的なOffice アプリ、インテリジェント クラウド サービス、世界レベルのセキュリティを組み合わせたもので、より多くの実現に役立ちます。

Microsoft 365には、組織が最新のWindows オペレーティング システムで作業していることを確認するのに役立つライセンスと機能が含まれています。 また、Windows、iOS、Android デバイスが、認証とデータ保護を必要とするポリシーに登録され、セキュリティで保護されていることを確認します。 さらに、Enterprise (以前に名前が付けられたOffice 365 ProPlus) クライアント ソフトウェアのWindows 10とMicrosoft 365 Appsは、最新の機能とセキュリティ更新プログラムを含めるために継続的に更新されます。
  
Microsoft 365は、Microsoft クラウドによって有効およびセキュリティで保護されているデバイスと生産性のエクスペリエンスを絶えず向上させることで、ビジネスをデジタル変革する方法です。
 
|関連情報|説明|
|---|---|
|[Microsoft 365](https://www.microsoft.com/microsoft-365)|Microsoft 365のバージョンに関する情報を取得します。|
|[ビジネス向けMicrosoft 365ドキュメント](../admin/index.yml)|中小企業向けのMicrosoft 365のバージョンに関する詳細な情報を取得します。|
|[教育機関向けドキュメントのMicrosoft 365](/microsoft-365/education/)|教育機関向けのMicrosoft 365のバージョンに関する詳細情報を取得します。|
|[EnterpriseドキュメントのMicrosoft 365](./index.yml)|エンタープライズ組織のMicrosoft 365のバージョンに関する詳細な情報を取得します。|
|||

## <a name="what-happens-if-i-dont-upgrade"></a>アップグレードしないとどうなりますか?

現時点ではアップグレードしないことを選択できます。 オンプレミスのサーバーとアプリケーションは引き続き実行されます。 ただし、セキュリティ更新プログラムやサポート オプションを受け取らなくなった場合、組織はセキュリティ違反に対して脆弱になる可能性があります。 近いうちにアップグレードを計画することを強くお勧めします。 オンプレミスのサーバーとアプリケーションのMicrosoft 365または新しいバージョンにアップグレードできます。

## <a name="what-upgrade-options-are-available"></a>利用可能なアップグレード オプションは何ですか?      

組織では、いくつかのアップグレード オプションを検討する必要があります。

- **オンプレミスのサーバーとアプリケーションをアップグレードします。** オンプレミスでOffice製品とサーバー アプリケーションを使用している場合は、次の計画コンテンツを参照してください。<br/> 

  |Office 2007 製品とサービス|Office 2010 製品とサービス|
  |---|---|
  |[Office 2007](/DeployOffice/office-2007-end-support-roadmap) (デスクトップ)|[Office 2010](/DeployOffice/office-2010-end-support-roadmap) (デスクトップ)|
  |[Exchange 2007](exchange-2007-end-of-support.md)|[Exchange 2010](exchange-2010-end-of-support.md)|
  |[SharePoint 2007](sharepoint-2007-end-of-support.md)|[SharePoint 2010](upgrade-from-sharepoint-2010.md)|
  |[Office Communications Server](/skypeforbusiness/plan-your-deployment/upgrade)|[Lync Server 2010](/skypeforbusiness/plan-your-deployment/upgrade)|
  |[Project Server 2007](project-server-2007-end-of-support.md)|[Project Server 2010](project-server-2010-end-of-support.md)|
  |[PerformancePoint Server 2007](pps-2007-end-of-support.md)||
 
- **Microsoft 365またはOffice 365を使用してハイブリッド ソリューションを実装します。** ハイブリッド ソリューションでは、オンプレミスのサーバーとアプリケーション、およびそれに相当するクラウドが使用されます。 段階的にクラウドに移行する場合、または一部のサーバーとアプリケーションをオンプレミスに保持する必要がある場合は、ハイブリッド ソリューションが組織に適している可能性があります。 詳細については、 [Microsoft クラウド アーキテクチャ モデルに関するページを](../solutions/cloud-architecture-models.md)参照してください。 
    
- **Microsoft 365またはOffice 365を使用してクラウドに移動します。** 多くのお客様にとって、クラウドへの移行は、効率的でコスト効率の高いソリューションです。 クラウドへの完全な移行により、セットアップと継続的な管理が容易になります。 このオプションでは、すべての最新の機能とセキュリティ更新プログラムがシームレスに提供されます。 詳細については、この記事の[「Microsoft 365とは」](#what-is-microsoft-365)セクションを参照してください。
    
## <a name="can-i-get-help-for-my-organization"></a>組織のヘルプを受けることができますか?

アップグレードの計画に関するヘルプが必要な場合は、次のオプションの 1 つ以上を検討してください。

- パートナーまたはボリューム ライセンススペシャリストと連携します。 [Microsoft 365パートナーまたはリセラーを見つけます](https://support.office.com/article/b6c18a9b-2aed-4c84-9d75-af709160258c.aspx)。 

- 組織がMicrosoft 365ライセンスの対象となる数を購入した場合は、FastTrack チームがセットアップ プロセスを支援します。 詳細については、「[Microsoft 365のFastTrack」を](https://www.microsoft.com/fasttrack/microsoft-365)参照してください。

- 小規模な組織の一員である場合、または組織のOfficeを自分でアップグレードする場合は、「[Microsoft 365 Business ユーザーを最新のOffice クライアントにアップグレードする](/office365/admin/setup/upgrade-users-to-latest-office-client)」を参照してください。 
  
## <a name="im-a-home-user-what-do-i-do"></a>私はホーム ユーザーです。 どうしたらよいでしょうか。

自宅で Office 2007 または Office 2010 を使用している場合は、次のアップグレード オプションを検討してください。

- **ブラウザーでOfficeを無料で使用します。** ブラウザーでOfficeファイルを作成、表示、編集します。 インターネット にアクセスできるほぼすべてのデバイスから、これらのファイルにアクセスできます。 

  [Office on the web](https://products.office.com/office-online/documents-spreadsheets-presentations-office-online)には[、Word for the web](https://go.microsoft.com/fwlink/p/?linkid=746664)、[Excel for the web](https://go.microsoft.com/fwlink/p/?linkid=746665)、[PowerPoint for the web](https://go.microsoft.com/fwlink/p/?linkid=746666)、[OneNote for the web](https://go.microsoft.com/fwlink/p/?linkid=746674)、[Swayが](https://go.microsoft.com/fwlink/p/?linkid=746675)含まれます、[電子メール](https://go.microsoft.com/fwlink/p/?linkid=746676)、[予定表](https://go.microsoft.com/fwlink/p/?linkid=746678)、[およびOneDrive](https://go.microsoft.com/fwlink/p/?linkid=746679)。 作業を開始するには、[Office.com](https://office.com) にアクセスし、[Microsoft アカウント](https://account.microsoft.com/account)を使用してサインインします。 Microsoft アカウントをお持ちでない場合は、[Office.com](https://office.com) で作成できます。

- **Microsoft 365 Family試してください。** [Microsoft 365 Family](https://www.microsoft.com/microsoft-365/p/microsoft-365-family/cfq7ttc0k5dm?rtc=2&activetab=pivot:overviewtab)の試用版を開始して、その動作を確認します。 Microsoft 365 Familyを使用すると、OneDriveでクラウド ストレージを楽しむことができます。

  Windows 7 のサポート[は、2020 年 1 月 14 日に終了しました](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)。 Office 365 Home または Excel Office 365 Personal で提供され、Windows 7 台のデバイスで実行される Word、PowerPoint、Outlook、Publisher、Access のバージョンは、セキュリティ更新プログラムを受け取りますが、機能更新プログラムは受け取りません。 これらのアプリケーションの機能更新プログラムを引き続き受信するには、[Windows 7 台のデバイスをWindows 10にアップグレードします](https://support.microsoft.com/help/12435/windows-10-upgrade-faq)。
    
- **自宅&amp;の学生Office購入します。** このオプションを選択した場合は、1 回限りの購入を行い、Windows PC または Mac にOfficeをインストールします。 この購入はサブスクリプションではありません。これは、1 台のコンピューターに対する 1 回限りの永続的使用ライセンスです。 [要件](https://office.com/systemrequirements)を表示し、バージョンを選択します。

  - Windows PC がWindows 10実行されている場合は、[ホーム & Student 2019 Office](https://www.microsoft.com/p/office-home-student-2019/cfq7ttc0k7c8)取得することを検討してください。

  - Windows PC が 7、8、または 8.1 Windows実行されていて、現在Windows 10にアップグレードしていない場合は、ホーム & Student 2016 または別のエディションのMicrosoft Office Office入手することを検討してください。 認定リセラーから入手できます。
     
    Windows 7 のサポート[は、2020 年 1 月 14 日に終了しました](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)。 Microsoft では、セキュリティ更新プログラムは提供されなくなりました。 Windows 7 台のデバイスをWindows 10にアップグレードして、継続的なセキュリティと機能の更新と継続的なサポートを行います。

今すぐアップグレードしないことを選択した場合、Office アプリはタイムラインに従って引き続き実行[されます](https://support.microsoft.com/lifecycle/search/13615)。 ただし、セキュリティ更新プログラムや新機能と改善された機能を入手するには、アップグレードする必要があります。
   
## <a name="next-steps"></a>次の手順

- [Office 2007 サーバー/クライアントからアップグレードする](upgrade-from-office-2007-servers-and-products.md)
- [Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
   
## <a name="related-topics"></a>関連項目
  
[Microsoft のライフサイクル ポリシー](/lifecycle/)