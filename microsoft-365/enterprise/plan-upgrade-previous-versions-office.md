---
title: 2007 または 2010 Office 2010 サーバーとクライアントからのアップグレードを計画する
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
description: この記事には、2007 年または 2010 年Office 2010 年Officeアップグレードの計画に役立つユーザー向けリソースが含まれている。
ms.openlocfilehash: 65f635e5c6195222ef2e39898cb1da2ee0dc0df0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927468"
---
# <a name="plan-your-upgrade-from-office-2007-or-office-2010-servers-and-clients"></a>Office 2007 または Office 2010 サーバー/クライアントからアップグレードする計画を立てる

*この記事は、Microsoft 365 for Enterprise および Office 365 for Enterprise の両方に適用されます。*

組織で古いバージョンの製品Office使用している場合は、アップグレードの計画を立て始めるのに最適な時期です。 Office 2007 製品とサービスはサポート [の最後に達しました](upgrade-from-office-2007-servers-and-products.md)。 2010 Officeサービスの場合:

- Office 2010 および Exchange 2010 は *、2020 年 10 月 13* 日にサポートの終了に達しました。 
- SharePoint 2010 および Project Server 2010 は、*2021年4月13日* にサポートが終了します。 

詳細については [、「Upgrade from Office 2010 サーバーとクライアント」を参照してください](upgrade-from-office-2010-servers-and-products.md)。

この記事のリソースを使用して、アップグレードを開始します。

## <a name="what-is-microsoft-365"></a>Microsoft 365 とは

[Microsoft 365](https://www.microsoft.com/microsoft-365) は、革新的な Office、インテリジェント クラウド サービス、世界クラスのセキュリティの組み合わせで、より多くの実現に役立ちます。

Microsoft 365 には、組織が最新の Windows オペレーティング システムで作業するためのライセンスと機能が含まれています。 また、Windows、iOS、Android デバイスが認証とデータ保護を必要とするポリシーに登録され、セキュリティで保護されます。 さらに、Windows 10 および Microsoft 365 Apps for Enterprise (以前は Office 365 ProPlus という名前) クライアント ソフトウェアが継続的に更新され、最新の機能とセキュリティ更新プログラムが含まれています。
  
Microsoft 365 は、Microsoft クラウドで有効でセキュリティで保護されたデバイスと生産性エクスペリエンスを絶えず向上させ、ビジネスをデジタル化する方法です。
 
|関連情報|説明|
|---|---|
|[Microsoft 365](https://www.microsoft.com/microsoft-365)|Microsoft 365 のバージョンに関する情報を取得します。|
|[Microsoft 365 for Business のドキュメント](../business/index.yml)|中小企業向け Microsoft 365 のバージョンに関する詳細情報を取得します。|
|[Microsoft 365 for Education ドキュメント](/microsoft-365/education/)|教育機関向け Microsoft 365 のバージョンに関する詳細情報を取得します。|
|[Microsoft 365 for Enterprise ドキュメント](./index.yml)|エンタープライズ組織向け Microsoft 365 のバージョンに関する詳細情報を取得します。|
|||

## <a name="what-happens-if-i-dont-upgrade"></a>アップグレードしない場合は、何が起こりますか?

現時点ではアップグレードしない選択が可能です。 オンプレミスのサーバーとアプリケーションは引き続き実行されます。 ただし、セキュリティ更新プログラムやサポート オプションを受け取らなくなった場合、組織はセキュリティ侵害に対して脆弱になる可能性があります。 アップグレードをすぐに計画することを強く推奨します。 Microsoft 365 または新しいバージョンのオンプレミス サーバーとアプリケーションにアップグレードできます。

## <a name="what-upgrade-options-are-available"></a>使用可能なアップグレード オプションは何ですか?      

組織では、いくつかのアップグレード オプションを検討する必要があります。

- **オンプレミスのサーバーとアプリケーションをアップグレードします。** オンプレミスの製品とサーバー Officeを使用している場合は、次の計画コンテンツを参照してください。<br/> 

  |Office 2007 製品とサービス|Office 2010 製品とサービス|
  |---|---|
  |[Office 2007](/DeployOffice/office-2007-end-support-roadmap) (デスクトップ)|[Office 2010](/DeployOffice/office-2010-end-support-roadmap) (デスクトップ)|
  |[Exchange 2007](exchange-2007-end-of-support.md)|[Exchange 2010](exchange-2010-end-of-support.md)|
  |[SharePoint 2007](sharepoint-2007-end-of-support.md)|[SharePoint 2010](upgrade-from-sharepoint-2010.md)|
  |[Office Communications Server](/skypeforbusiness/plan-your-deployment/upgrade)|[Lync Server 2010](/skypeforbusiness/plan-your-deployment/upgrade)|
  |[Project Server 2007](project-server-2007-end-of-support.md)|[Project Server 2010](project-server-2010-end-of-support.md)|
  |[PerformancePoint Server 2007](pps-2007-end-of-support.md)||
 
- **Microsoft 365 または Microsoft 365 または microsoft 365 Office実装します。** ハイブリッド ソリューションでは、オンプレミスのサーバーとアプリケーション、およびそれらのクラウド同等物を使用します。 段階的にクラウドに移行する場合や、一部のサーバーとアプリケーションをオンプレミスに保持する必要がある場合は、組織に合ったハイブリッド ソリューションが適切な場合があります。 詳細については、「Microsoft クラウド アーキテクチャ [モデル」を参照してください](../solutions/cloud-architecture-models.md)。 
    
- **Microsoft 365 または microsoft 365 または Officeに移動します。** 多くのお客様の場合、クラウドへの移行は効率的でコスト効率の高いソリューションです。 クラウドへの完全な移行により、セットアップと継続的な管理が容易になります。 このオプションは、すべての最新の機能とセキュリティ更新プログラムをシームレスに提供します。 詳細については、この記事の [「Microsoft 365 とは」](#what-is-microsoft-365) セクションを参照してください。
    
## <a name="can-i-get-help-for-my-organization"></a>組織のヘルプを受け取れるか?

アップグレードの計画に関するヘルプが必要な場合は、次のオプションの 1 つ以上を検討してください。

- パートナーまたはボリューム ライセンススペシャリストと一緒に作業します。 [Microsoft 365 パートナーまたはリセラーを検索します](https://support.office.com/article/b6c18a9b-2aed-4c84-9d75-af709160258c.aspx)。 

- 組織が対象となる数の Microsoft 365 ライセンスを購入した場合、FastTrack チームがセットアップ プロセスを支援します。 詳細については [、「FastTrack for Microsoft 365」を参照してください](https://www.microsoft.com/fasttrack/microsoft-365)。

- 小規模な組織の一部である場合、または組織の Office アップグレードを自分で処理する場合は [、「Microsoft 365 Business](/office365/admin/setup/upgrade-users-to-latest-office-client)ユーザーを最新の Office クライアントにアップグレードする」を参照してください。 
  
## <a name="im-a-home-user-what-do-i-do"></a>私はホーム ユーザーです。 どうしたらよいでしょうか。

2007 または 2010 Office 2010 Officeを使用している場合は、次のアップグレード オプションを検討してください。

- **ブラウザー Officeを無料で使用します。** ブラウザーでファイルを作成、表示Office編集します。 インターネットにアクセスできるデバイスに関する情報から、これらのファイルにアクセスできます。 

  [Office](https://products.office.com/office-online/documents-spreadsheets-presentations-office-online)には[、Word for the web](https://go.microsoft.com/fwlink/p/?linkid=746664) [、Excel for](https://go.microsoft.com/fwlink/p/?linkid=746665)the [web、PowerPoint for](https://go.microsoft.com/fwlink/p/?linkid=746666)the [Web、OneNote for](https://go.microsoft.com/fwlink/p/?linkid=746674)the Web、Sway、Email、Calendar、および[OneDrive](https://go.microsoft.com/fwlink/p/?linkid=746679)が含まれます。 [](https://go.microsoft.com/fwlink/p/?linkid=746675) [](https://go.microsoft.com/fwlink/p/?linkid=746676) [](https://go.microsoft.com/fwlink/p/?linkid=746678) 開始するには、Microsoft アカウントを [使用 Office.com](https://office.com) にアクセスしてサインイン [します](https://account.microsoft.com/account)。 Microsoft アカウントをお持ちでない場合は、Microsoft アカウントで作成[Office.com。](https://office.com)

- **Microsoft 365 ファミリを試してみてください。** [Microsoft 365 ファミリの試用版を開始して](https://www.microsoft.com/microsoft-365/p/microsoft-365-family/cfq7ttc0k5dm?rtc=2&activetab=pivot:overviewtab)、その動作を確認します。 Microsoft 365 ファミリを使用すると、OneDrive でクラウド ストレージを利用できます。

  Windows 7 のサポート [は 2020 年 1 月 14 日に終了しました](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)。 Office 365 Home または Office 365 Personal で提供され、Windows 7 デバイスで実行される Word、Excel、PowerPoint、Outlook、Publisher、Access のバージョンは、セキュリティ更新プログラムを受け取りますが、機能更新プログラムは受け取ります。 これらのアプリケーションの機能更新プログラムを引き続き受信するには、Windows 7 デバイスを [Windows 10 にアップグレードします](https://support.microsoft.com/help/12435/windows-10-upgrade-faq)。
    
- **ホームOfficeを購入 &amp; します。** このオプションを選択した場合は、1 回の購入を行い、Windows PC または Mac Officeインストールします。 この購入はサブスクリプションではない。これは、1 つのコンピューターに対して 1 回の永続的な使用ライセンスです。 要件を [表示し、](https://office.com/systemrequirements) バージョンを選択します。

  - Windows PC で Windows 10 が実行されている場合は、ホーム Office [2019](https://www.microsoft.com/p/office-home-student-2019/cfq7ttc0k7c8)&を検討してください。

  - Windows PC で Windows 7、8、または 8.1 が実行され、Windows 10 にアップグレードしていない場合は、Office Home & Student 2016 または別のエディションの Microsoft Office を取得する方法を検討してください。 認定リセラーから取得できます。
     
    Windows 7 のサポート [は 2020 年 1 月 14 日に終了しました](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support)。 Microsoft はセキュリティ更新プログラムを提供しなくなりました。 Windows 7 デバイスを Windows 10 にアップグレードして、継続的なセキュリティと機能の更新プログラムと継続的なサポートを提供します。

今すぐアップグレードしない場合は、Officeに従ってアプリが [実行されます](https://support.microsoft.com/lifecycle/search/13615)。 ただし、セキュリティ更新プログラムや新機能や強化された機能を取得するには、アップグレードする必要があります。
   
## <a name="next-steps"></a>次の手順

- [Office 2007 サーバー/クライアントからアップグレードする](upgrade-from-office-2007-servers-and-products.md)
- [Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
   
## <a name="related-topics"></a>関連項目
  
[Microsoft のライフサイクル ポリシー](/lifecycle/)