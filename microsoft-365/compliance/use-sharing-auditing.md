---
title: 監査ログで共有監査を使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 管理者は、組織外のユーザーと共有されるリソースを識別するために、Microsoft 365監査ログで共有監査を使用する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff05b655617608332b4b838e07a6af55e8b4d010
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193173"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>監査ログで共有監査を使用する

共有は、オンラインおよび SharePointおよびOneDrive for Businessの重要なアクティビティであり、組織で広く使用されています。 管理者は、監査ログの共有監査を使用して、組織内での共有の使用方法を判断できます。 
  
## <a name="the-sharepoint-sharing-schema"></a>共有SharePointスキーマ

共有イベント (共有ポリシーや共有リンクに関連するイベントを含む) は、ファイル関連イベントやフォルダー関連のイベントとは一つの主な方法で異なります。あるユーザーは、別のユーザーに影響を与えるアクションを実行しています。 たとえば、リソースユーザー A がユーザー B にファイルへのアクセス権を与える場合です。 この例では、ユーザー A はユーザー  *であり*  、ユーザー B はターゲット  *ユーザーです*。 ファイル スキーマSharePoint、ユーザーの操作はファイル自体にのみ影響します。 ユーザー A がファイルを開くと **、FileAccessed** イベントで必要な唯一の情報は、実際のユーザーです。 この違いに対処するために、共有イベントの詳細をキャプチャする SharePoint共有スキーマ *と呼* ばれる別のスキーマがあります。 これにより、管理者は、リソースを共有したユーザーとリソースが共有されたユーザーを表示できます。 
  
共有スキーマは、共有イベントに関連する監査レコードに 2 つの追加フィールドを提供します。 
  
- **TargetUserOrGroupType:** ターゲット ユーザーまたはグループがメンバー、ゲスト、SharePointGroup、SecurityGroup、またはパートナーであるかどうかを識別します。

- **TargetUserOrGroupName:** リソースが共有されたターゲット ユーザーまたはグループの UPN または名前を格納します (前の例のユーザー B)。 

これら 2 つのフィールドは、ユーザー、操作、日付などの監査ログ スキーマの他のプロパティに加えて、どのユーザーが誰といつどのリソースを共有したのかを完全に伝 *えます*。  
  
共有ストーリーに重要な別のスキーマ プロパティがあります。 監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの **AuditData** 列に、共有イベントに関する情報が格納されます。 たとえば、ユーザーがサイトを別のユーザーと共有する場合、ターゲット ユーザーを別のユーザー グループに追加SharePointします。 **AuditData 列は**、この情報をキャプチャして管理者のコンテキストを提供します。 AuditData [列の情報](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) を解析する方法については、手順 2 **を参照** してください。

## <a name="sharepoint-sharing-events"></a>SharePoint共有イベント

共有は、ユーザー (作用ユーザー)がリソースを別のユーザー (ターゲット ユーザー) と共有する場合に *定義* されます。 リソースを外部ユーザー (組織の外部にいて、組織の Azure Active Directory にゲスト アカウントを持ってないユーザー) との共有に関連する監査レコードは、監査ログに記録される次のイベントによって識別されます。

- **SharingInvitationCreated:** 組織内のユーザーがリソース (サイトの可能性がある) を外部ユーザーと共有しようとした。 これにより、外部共有の招待がターゲット ユーザーに送信されます。 この時点では、リソースへのアクセスは許可されません。

- **SharingInvitationAccepted:** 外部ユーザーは、そのユーザーが送信した共有の招待を受け入れ、リソースにアクセスできます。

- **AnonymousLinkCreated:** リソースに対して匿名リンク ("Anyone" リンクとも呼ばれる) が作成されます。 匿名リンクを作成してからコピーすることができますので、匿名リンクを持つドキュメントがターゲット ユーザーと共有されたと見なすのが妥当です。

- **AnonymousLinkUsed:** 名前が示すように、このイベントは、匿名リンクを使用してリソースにアクセスするときに記録されます。 

- **SecureLinkCreated:** ユーザーが特定のユーザーとリソースを共有する "特定のユーザー リンク" を作成しました。 このターゲット ユーザーは、組織外のユーザーである可能性があります。 リソースが共有されているユーザーは **、AddedToSecureLink** イベントの監査レコードで識別されます。 これら 2 つのイベントのタイム スタンプは、ほぼ同じです。

- **AddedToSecureLink:** ユーザーが特定のユーザー リンクに追加されました。 このイベントの **TargetUserOrGroupName** フィールドを使用して、対応する特定のユーザー リンクに追加されたユーザーを識別します。 このターゲット ユーザーは、組織外のユーザーである可能性があります。

## <a name="sharing-auditing-work-flow"></a>監査の作業フローの共有
  
ユーザー (作用するユーザー) がリソースを別のユーザー (ターゲット ユーザー) と共有する場合、SharePoint (または OneDrive for Business) は、ターゲット ユーザーの電子メール アドレスが組織のディレクトリ内のユーザー アカウントに既に関連付けられているか最初に確認します。 ターゲット ユーザーがディレクトリに (対応するゲスト ユーザー アカウントを持つ) 場合、SharePointを実行します。
  
-  ターゲット ユーザーを適切なグループに追加して、リソースにアクセスするターゲット ユーザーのアクセス許可をすぐに割り当て **、AddedToGroup** イベントSharePointログに記録します。 
    
- 共有通知をターゲット ユーザーの電子メール アドレスに送信します。
    
- **SharingSet イベントをログに記録** します。 このイベントには、監査ログ検索ツールのアクティビティ ピッカーの [共有とアクセス要求のアクティビティ] の下に、"共有ファイル、フォルダー、またはサイト" という名前のフレンドリーな名前が付きます。 手順 1 のスクリーンショット [を参照してください](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)。 
    
ターゲット ユーザーのユーザー アカウントがディレクトリに存在しない場合、SharePointを実行します。 
    
   - リソースの共有方法に基づいて、次のいずれかのイベントをログに記録します。
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (このイベントは、共有リソースがサイトの場合にのみログに記録されます)
    
   - ターゲット ユーザーが (招待内のリンクをクリックして) 送信された共有招待を受け入れる場合、SharePoint は **SharingInvitationAccepted** イベントをログに記録し、リソースにアクセスするためのターゲット ユーザーのアクセス許可を割り当てる。 ターゲット ユーザーに匿名リンクが送信された場合、ターゲット ユーザーがリンクを使用してリソースにアクセスした後 **、AnonymousLinkUsed** イベントがログに記録されます。 セキュリティで保護されたリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスすると **、FileAccessed** イベントがログに記録されます。

招待先のユーザーの ID や、招待を受け入れるユーザーなど、ターゲット ユーザーに関する追加情報も記録されます。 場合によっては、これらのユーザー (または電子メール アドレス) が異なる場合があります。 

## <a name="how-to-identify-resources-shared-with-external-users"></a>外部ユーザーと共有されているリソースを識別する方法

管理者の一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成します。 管理者は、共有監査をOffice 365、この一覧を生成できます。 これを行うには、次の操作を実行します。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>手順 1: 共有イベントを検索し、CSV ファイルに結果をエクスポートする

最初の手順は、監査ログで共有イベントを検索します。 監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「監査ログの検索 [」を参照してください](search-the-audit-log-in-security-and-compliance.md)。
  
1. <https://compliance.microsoft.com> に移動します。

2. 職場または学校のアカウントを使用してサインインします。

3. Microsoft 365 コンプライアンス センターの左側のウィンドウで、**[監査]** をクリックします。

    [**監査**] ページが表示されます。

4. [ **アクティビティ] で**、[ **共有とアクセス要求アクティビティ] をクリックして** 、共有関連イベントを検索します。 

    ![[アクティビティ] で、[要求アクティビティの共有とアクセス] を選択します。](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. 日付と時刻の範囲を選択して、その期間中に発生した共有イベントを検索します。 

6. [検索 **] を** クリックして検索を実行します。 

7. 検索の実行が完了し、結果が表示された場合は、[結果のエクスポート] **をクリックしてすべての結果** \> **をダウンロードします**。

    エクスポート オプションを選択すると、ウィンドウの下部にあるメッセージで、CSV ファイルを開くまたは保存するように求めるメッセージが表示されます。

8. [ **名前を** \> **付けて保存]** をクリックし、CSV ファイルをローカル コンピューターのフォルダーに保存します。 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>手順 2: PowerQuery エディターを使用してエクスポートされた監査ログの書式を設定する

次の手順では、Excel の Power Query Editor の JSON 変換機能を使用して **、AuditData** 列 (複数プロパティ JSON オブジェクトで構成される) の各プロパティを独自の列に分割します。 これにより、列をフィルター処理して、共有に関連するレコードを表示できます。

詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する」を参照してください。

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>手順 3: 外部ユーザーと共有するリソースの CSV ファイルをフィルター処理する

次の手順では、「共有イベントの共有」セクションで前述したさまざまな共有関連イベントに対して[CSV をSharePointします](#sharepoint-sharing-events)。 または **、TargetUserOrGroupType** 列をフィルター処理して、このプロパティの値が Guest であるすべてのレコードを **表示できます**。 

前の手順に従って、PowerQuery エディターを使用して CSV ファイルを準備した後、次の手順を実行します。
    
1. 手順 2 でExcelしたファイルを開きます。 

2. [ホーム] **タブで** 、[フィルターの並 **べ替え&] をクリック** し、[フィルター] を **クリックします**。
    
3. [操作]**列&** [フィルターの並べ替え] ドロップダウン リストで、すべての選択をクリアし、次の共有関連イベントを 1 つ以上選択し **、[OK] をクリックします**。
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel選択したイベントの行が表示されます。
    
4. **TargetUserOrGroupType という名前の列に移動し**、選択します。 
    
5. [フィルター **の並べ&] ドロップダウン** リストで、すべての選択をクリアし **、[TargetUserOrGroupType:Guest]** を選択し **、[OK] をクリックします**。
    
    外部Excel **TargetUserOrGroupType:Guest** の値で識別されるので、共有イベントの行と、ターゲット ユーザーが組織の外部にある場所を表示します。 
  
> [!TIP]
> 表示される監査レコードの場合 **、ObjectId** 列は、ターゲット ユーザーと共有されたリソースを識別します。たとえば  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
