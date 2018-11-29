---
title: GDPR に関する Intune データ主体要求
description: ''
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
author: dougeby
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
ms.collection: GDPR
ms.openlocfilehash: eeb50954f849b0c110a88cc7d768844847d99255
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869632"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>GDPR に関する Intune データ主体要求
EU データ保護規則 (GDPR) では、ユーザー (規則では*データ サブジェクト*と呼ばれる) に対して、雇用主やその他の会社または組織 (*データ コントローラー*または単に*コントローラー*と呼ばれる) が収集した個人データを管理する権利を与えます。GDPR の下で個人データは広範な定義がなされ、識別された、または識別可能な自然人と関連するあらゆるデータのことです。GDPR は個人データに対するデータ サブジェクト固有の権利を与えます。この権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、または、別のコントローラーに移動できるようにするための電子形式での受信が含まれます。データ サブジェクトからコントローラーに個人データへのアクション実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。

このガイドでは、DSR への対応として個人データを見つけて処理するコントローラーのお客様を支援する目的で、Microsoft の製品、サービス、管理ツールをどのように使用できるかを説明します。特に、Microsoft クラウドにある個人データを検出、アクセス、処理する方法を示します。このガイドで説明するプロセスの概要は次のとおりです:

1.  ***検出***—検索/検出ツールを使用することで、DSR の対象となる可能性がある顧客データをより簡単に見つけます。対応の対象となり得るドキュメントが収集されたら、後続のステップの DSR アクションを 1 つ以上実行することで要求に対応できます。あるいは、DSR 対応に関する組織のガイドラインを要求が満たしていないと判断する場合もあります。

2.  ***評価***—Microsoft クラウドにある個人データを取り出し、コピーが要求されている場合には、データ サブジェクトが利用できる形でコピーを作成します。

3.  ***修正***—要求されたアクションに応じて個人データを変更したり、他の操作を実行したりします。

4.  ***制限***—さまざまな Azure サービスのライセンスを削除するか、該当するサービスを無効にする (可能な場合) ことで、個人データの処理を制限します。また、データを Microsoft クラウドから削除してオンプレミスまたは別の場所で保持することもできます。

5.  ***削除***—Microsoft クラウドに格納されていた個人データを完全に削除します。

6.  ***エクスポート***—個人データの電子的コピー (マシンで読み取り可能な形式) をデータ サブジェクトに提供します。

このガイドの各セクションでは、Microsoft クラウド内の個人データに関する DSR への対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>用語集

このガイドに関連する用語を以下に定義します。

-   *コントローラー*—単独で、または他者と共同で、個人データの処理の目的と手段を決定する個人または法人、公的機関、団体、その他の組織。そのような処理の目的と手段が ＥＵ 法もしくは構成国法によって決定される場合、コントローラーまたはその指名に関する具体的な基準が ＥＵ 法もしくは構成国法によって提供される場合があります。

-   *個人データ*および*データ主体*—特定される個人、または特定可能な個人 ('データ主体') に関連するあらゆる情報であり、特定可能な個人とは、その個人の名前、ID 番号、位置データ、オンライン ID、または物理的、生理学的、遺伝子上、心理的、経済的、文化的、社会的な識別情報に固有の 1 つ以上の因子を参照することによって直接または間接的に特定される人物です。

-   *プロセッサ*—コントローラーに代わって個人データを処理する個人または法人、公的機関、団体、その他の組織。

-   *顧客データ*—お客様または代理者がエンタープライズ サービスの使用を通じて Microsoft に提供する、すべてのテキスト、サウンド、ビデオ、イメージ ファイルを含むすべてのデータ。顧客データには次の両方が含まれます: (1) エンド ユーザーの個人情報 (たとえば Azure Active Directory でのユーザー名と連絡先情報)、特定のサービスでお客様がアップロードまたは作成したカスタマー コンテンツ (たとえば Azure Storage アカウント内のカスタマー コンテンツ、Azure SQL Database のカスタマー コンテンツ、Azure Virtual Machines でのお客様の仮想マシン イメージ)。

-   *システム生成ログ*—Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。システム生成ログには主に固有 ID などの仮名化データが含まれています。固有 ID とは通常、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。また、ユーザー名などのエンド ユーザー個人情報がシステム生成ログに含まれることもあります。  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>このガイドの使用方法

このガイドは次のような 2 部構成になっています。

**第 1 部: 顧客データに関するデータ サブジェクト要求に対応する** — このガイドの第 1 部では、アプリケーションで作成されたデータにアクセスし、データを修正、制限、削除、エクスポートする方法を示します。このセクションでは、カスタマー コンテンツとエンド ユーザー個人情報の両方に対して DSR を実行する方法について詳しく述べます。

**第 2 部: システム生成ログに関するデータ サブジェクト要求に対応する** — Microsoft のエンタープライズ サービスを利用する際、Microsoft がサービスを提供するために使われるシステム生成ログという情報が生成されます。このガイドの第 2 部では、Azure でこのような情報にアクセスし、それを削除したりエクスポートしたりする方法について述べます。

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Azure Active Directory および Microsoft Intune に関する DSR について

お客様企業へのサービス提供を考慮するとき、特定の Azure Active Directory (AAD) テナント内のコンテキストで常に DSR の実行について理解する必要があります。特に、DSR は特定の AAD テナントの内部で常に実行されます。あるユーザーが複数のテナントに参加する場合、要求を受け取った特定のテナントのコンテキスト内で*のみ*、その DSR が実行されることを強調することが重要です。あるお客様企業からの DSR を実行しても、隣接するお客様企業のデータは影響を**受けない**という点を理解することは重要です。

また、企業顧客に提供される Microsoft Intune に関しても同じことが当てはまります。*ある AAD テナントに関連付けられた* Intune アカウントに対する DSR の実行では、そのテナント内のデータ**のみ**が対象になります。さらに、テナント内の Intune アカウントを扱う際には次の点を理解することが重要です。

-   Intune ユーザーが Azure サブスクリプションを作成すると、そのサブスクリプションは AAD テナントであるかのように扱われます。その結果、DSR の範囲は上記のようにテナント内となります。

-   Intune アカウントを介して作成された Azure サブスクリプションが削除された場合、実際の Intune アカウントには影響が**ありません**。ここでも、上記のように、Azure サブスクリプション内で実行される DSR はテナント自体の範囲に限定されます。

**特定のテナント外部の** Intune アカウント自体に対する DSR は、カスタマー プライバシー ダッシュボードを介して実行されます。詳しくは、Windows データ主体要求ガイドを参照してください。

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>第 1 部: 顧客データに関する DSR ガイド

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>顧客データに対する DSR の実行

Microsoft の特定のお客様データにアクセスし、それを削除したりエクスポートしたりするには、Azure ポータルを使用するか、特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) やユーザー インターフェイス (UI) を直接使用できます (後者は*製品内エクスペリエンス*とも呼ばれます)。このような製品内エクスペリエンスについての詳細は、各サービスの参照ドキュメントに記載されています。

>[!Important]  
>製品内 DSR をサポートするサービスでは、そのサービスのアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を直接使用し、該当する CRUD (作成、読み取り、更新、削除) 操作を記述する必要があります。したがって、特定のデータ サブジェクトの要求全体を完了するには Azure ポータル内での DSR 実行に加えて特定のサービス内で DSR を実行する必要があります。詳細については、特定のサービスの参照ドキュメントをご覧ください。

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>ステップ 1: 検出

DSR への対応の第一歩は、要求の対象となる個人データを見つけることです。この第 1 ステップ (該当する個人データの検出と確認) により、DSR の承認/拒否に関する組織の要件を DSR が満たしているかどうか判断できます。たとえば、該当する個人データを検出して確認した後、その要求を実行すると他者の権利や自由が侵害される恐れがあるので、その要求は組織の要件に適合しないと判断する場合があるでしょう。

データを見つけた後、データ主体による要求を満たすために特定のアクションを実行できます。詳細については、以下を参照してください。
- [データ収集](https://docs.microsoft.com/intune/privacy-data-collect)
- [データの保存と処理](https://docs.microsoft.com/intune/privacy-data-store-process)
- [個人データの表示](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>ステップ 2: アクセス
DSR 対応の対象となる可能性のある個人データを含む顧客データが見つかった後、組織とその担当者はどんなデータをデータ サブジェクトに提供するかを決定します。実際のドキュメントのコピー、適切に編集したバージョン、または共有できると判断した部分のスクリーン ショットを提供できます。アクセス要求に対するこのような対応ごとに、対象のデータを含むドキュメントのコピーまたは他のアイテムを取得する必要があります。

データ サブジェクトにコピーを提供する際には、他のデータ サブジェクトに関する個人情報や他の機密情報を削除または編集する必要が生じることがあります。

<span id="_Using_Content_Search_1" class="anchor"></span>DSR アクセス要求への対応としてデータのコピーを取得する方法を以下で説明します。

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介して DSR アクセス要求を管理できます。DSR アクセス要求では (a) エンド ユーザーに関する個人情報、および (b) システム生成ログを含むユーザー個人データへのアクセスが扱われます。

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>サービス固有のインターフェイス

Microsoft Intune は、ユーザー インターフェイス (UI) または既存のアプリケーション プログラミング インターフェイス (API) を介して直接[顧客データを検出する](#step-1-discover)機能を提供します。

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>ステップ 3: 修正

組織のデータに含まれる個人データを修正するようにデータ主体が依頼した場合は、組織とその担当者がその依頼を承認するのが適切かどうか判断する必要があります。データの修正には、ドキュメントまたはその他の種類のアイテムの中の個人データの編集、変更、削除などのアクションの実行が含まれます。 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 データ プロセッサとして Microsoft は、システム生成ログを修正する機能を提供していません。これは、このログが実際のアクティビティを反映しており、Microsoft サービス内のイベントの履歴レコードを構成しているためです。Intune に関しては、管理者はデバイスまたはアプリ固有の情報を更新できません。エンドユーザーが個人データ (デバイス名など) を修正したい場合は、デバイス上で直接行う必要があります。このような変更は、次に Intune に接続したときに同期されます。

### <a name="step-4-restrict"></a>ステップ 4: 制限

<span id="_Delete" class="anchor"></span>個人データの処理を制限するようデータ主体から依頼されることがあります。その場合、Azure ポータルと既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) の両方を使用できます。お客様企業のテナント管理者はこれらのエクスペリエンスを利用し、データ エクスポートとデータ削除を組み合わせて、このような DSR を管理できます。詳細については、「[個人データの処理](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)」を参照してください。

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>ステップ 5: 削除

組織の顧客データから個人データを削除することによる「消去する権利」は、GDPR における重要な保護です。個人データの削除には、監査ログ情報を除く、すべての個人データとシステム生成ログの削除が含まれます。詳細については、「[エンドユーザーの個人データの削除](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data)」を参照してください。


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>第 2 部: システム生成ログ
監査ログは、Microsoft Intune 内で変更を発生させるアクティビティの記録をテナント管理者に提供します。監査ログは、さまざまな管理アクティビティと、通常は、作成、更新 (編集)、削除、および割り当てアクションに使用できます。監査イベントを生成するリモート タスクを確認することもできます。これらの監査ログに、デバイスが Intune に登録されているユーザーからの個人データが含まれている場合があります。管理者は、監査ログを削除できません。詳細については、「[個人データの監査](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data)」を参照してください。


## <a name="notify-about-exporting-or-deleting-issues"></a>エクスポートまたは削除に関する問題を通知する
Azure portal でデータをエクスポートまたは削除中に問題が発生した場合は、Azure ポータルの **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理] > [他のセキュリティとコンプライアンスの要求] > [プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。

#### <a name="learn-more"></a>詳細情報
[Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)