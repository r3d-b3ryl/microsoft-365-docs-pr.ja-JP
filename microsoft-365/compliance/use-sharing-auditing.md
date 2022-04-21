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
description: 管理者は、Microsoft 365監査ログで共有監査を使用して、組織外のユーザーと共有されているリソースを識別する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 785fdd2628a1e0bea9fd0361e7843939bf7b84a3
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64999676"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>監査ログで共有監査を使用する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

共有は、SharePoint Online とOneDrive for Businessの重要なアクティビティであり、組織で広く使用されています。 管理者は、監査ログの共有監査を使用して、組織内での共有の使用方法を決定できます。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint共有スキーマ

共有イベント (共有ポリシーや共有リンクに関連するイベントを含まない) は、ファイル関連のイベントやフォルダー関連のイベントとは主に異なります。1 人のユーザーが別のユーザーに影響を与えるアクションを実行しています。 たとえば、リソースユーザー A がユーザー B にファイルへのアクセス権を与えた場合などです。 この例では、ユーザー A は  *代理ユーザー*  であり、ユーザー B は  *ターゲット ユーザー* です。 SharePoint ファイル スキーマでは、動作しているユーザーのアクションはファイル自体にのみ影響します。 ユーザー A がファイルを開くと、 **FileAccessed** イベントで必要な情報は、代理ユーザーだけです。 この違いに対処するために、SharePoint共有スキーマと呼ばれる別のスキーマがあり、イベントの共有に関する詳細情報をキャプチャ *します*。 これにより、管理者は、リソースを共有したユーザーとリソースが共有されたユーザーを把握できるようになります。 
  
共有スキーマには、共有イベントに関連する監査レコードに 2 つの追加フィールドが用意されています。 
  
- **TargetUserOrGroupType:** ターゲット ユーザーまたはグループがメンバー、ゲスト、SharePointGroup、SecurityGroup、またはパートナーであるかどうかを識別します。

- **TargetUserOrGroupName:** リソースが共有されたターゲット ユーザーまたはグループの UPN または名前を格納します (前の例のユーザー B)。 

これら 2 つのフィールドは、監査ログ スキーマの他のプロパティ (ユーザー、操作、日付など) に加えて、*どの* ユーザーが *誰* と *いつ* どのリソースを共有 *したかについて* の完全なストーリーを伝えることができます。 
  
共有ストーリーにとって重要な別のスキーマ プロパティがあります。 監査ログの検索結果をエクスポートすると、エクスポートされた CSV ファイルの **AuditData** 列に、イベントの共有に関する情報が格納されます。 たとえば、ユーザーが別のユーザーとサイトを共有する場合、これはターゲット ユーザーをSharePoint グループに追加することによって実現されます。 **AuditData** 列は、管理者にコンテキストを提供するために、この情報をキャプチャします。 **AuditData** 列の情報を解析する方法については、[手順 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) を参照してください。

## <a name="sharepoint-sharing-events"></a>イベントの共有SharePoint

共有は、ユーザー ( *代理* ユーザー) が別のユーザー ( *ターゲット* ユーザー) とリソースを共有する場合に定義されます。 外部ユーザー (組織の外部にあり、組織のAzure Active Directoryにゲスト アカウントを持たないユーザー) とのリソースの共有に関連する監査レコードは、監査ログに記録される次のイベントによって識別されます。

- **SharingInvitationCreated:** 組織内のユーザーが、リソース (サイトと考えられる) を外部ユーザーと共有しようとしました。 これにより、外部共有の招待がターゲット ユーザーに送信されます。 この時点では、リソースへのアクセスは許可されません。

- **SharingInvitationAccepted:** 外部ユーザーは、代理ユーザーから送信された共有招待を受け入れ、リソースにアクセスできるようになりました。

- **AnonymousLinkCreated:** リソースに対して匿名リンク ("すべてのユーザー" リンクとも呼ばれます) が作成されます。 匿名リンクを作成してコピーできるため、匿名リンクを持つすべてのドキュメントがターゲット ユーザーと共有されていると見なすのが妥当です。

- **AnonymousLinkUsed:** 名前が示すように、匿名リンクを使用してリソースにアクセスすると、このイベントがログに記録されます。 

- **SecureLinkCreated:** ユーザーが、特定のユーザーとリソースを共有するための "特定のユーザーリンク" を作成しました。 このターゲット ユーザーは、組織の外部にいるユーザーである可能性があります。 リソースが共有されているユーザーは、 **AddedToSecureLink** イベントの監査レコードで識別されます。 これら 2 つのイベントのタイムスタンプはほぼ同じです。

- **AddedToSecureLink:** 特定のユーザー のリンクにユーザーが追加されました。 このイベントの **TargetUserOrGroupName** フィールドを使用して、対応する特定のユーザー リンクに追加されたユーザーを識別します。 このターゲット ユーザーは、組織の外部にいるユーザーである可能性があります。

## <a name="sharing-auditing-work-flow"></a>監査ワークフローの共有
  
ユーザー (代理ユーザー) が別のユーザー (ターゲット ユーザー) とリソースを共有する場合、SharePoint (またはOneDrive for Business) は、最初に、ターゲット ユーザーの電子メール アドレスが組織のディレクトリ内のユーザー アカウントに既に関連付けられているかどうかを確認します。 ターゲット ユーザーがディレクトリ内にあり (対応するゲスト ユーザー アカウントを持つ) 場合、SharePoint次のことを行います。
  
-  ターゲット ユーザーを適切なSharePoint グループに追加して、リソースにアクセスするためのターゲット ユーザーのアクセス許可をすぐに割り当て、**AddedToGroup** イベントをログに記録します。 
    
- ターゲット ユーザーのメール アドレスに共有通知を送信します。
    
- SharingSet イベントをログに **記録します** 。 このイベントには、監査ログ検索ツールのアクティビティ ピッカーの **[共有とアクセス要求アクティビティ** ] の下にある "共有ファイル、フォルダー、またはサイト" というフレンドリ名があります。 [手順 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file) のスクリーンショットを参照してください。 
    
ターゲット ユーザーのユーザー アカウントがディレクトリ内にない場合、SharePointは次の処理を行います。 
    
   - リソースの共有方法に基づいて、次のいずれかのイベントをログに記録します。
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (このイベントは、共有リソースがサイトの場合にのみログに記録されます)
    
   - ターゲット ユーザーが (招待のリンクをクリックして) 送信された共有招待を受け入れると、**SharePoint SharingInvitationAccepted** イベントをログに記録し、ターゲット ユーザーにリソースにアクセスするためのアクセス許可を割り当てます。 ターゲット ユーザーに匿名リンクが送信された場合、ターゲット ユーザーがリンクを使用してリソースにアクセスした後、 **AnonymousLinkUsed** イベントがログに記録されます。 セキュリティで保護されたリンクの場合、外部ユーザーがリンクを使用してリソースにアクセスすると、 **FileAccessed** イベントがログに記録されます。

ターゲット ユーザーに関する追加情報 (招待の対象ユーザーの ID、招待を受け入れたユーザーなど) もログに記録されます。 場合によっては、これらのユーザー (または電子メール アドレス) が異なる場合があります。 

## <a name="how-to-identify-resources-shared-with-external-users"></a>外部ユーザーと共有されているリソースを識別する方法

管理者の一般的な要件は、組織外のユーザーと共有されているすべてのリソースの一覧を作成することです。 Office 365で共有監査を使用することで、管理者はこの一覧を生成できます。 これを行うには、次の操作を実行します。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>手順 1: 共有イベントを検索し、結果を CSV ファイルにエクスポートする

最初の手順では、イベントを共有するために監査ログを検索します。 監査ログの検索に関する詳細 (必要なアクセス許可を含む) については、「 [監査ログの検索」を](search-the-audit-log-in-security-and-compliance.md)参照してください。
  
1. <https://compliance.microsoft.com> に移動します。

2. 職場または学校のアカウントを使用してサインインします。

3. Microsoft Purview コンプライアンス ポータルの左側のウィンドウで、[ **監査**] をクリックします。

    [**監査**] ページが表示されます。

4. [ **アクティビティ**] の [ **共有とアクセス要求アクティビティ** ] をクリックして、共有関連のイベントを検索します。 

    ![[アクティビティ] で、[共有とアクセス要求アクティビティ] を選択します。](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. 日付と時刻の範囲を選択して、その期間内に発生した共有イベントを検索します。 

6. [ **検索** ] をクリックして検索を実行します。 

7. 検索の実行が完了し、結果が表示されたら、[ **結果** \> **をすべてダウンロード** する] をクリックします。

    エクスポート オプションを選択すると、ウィンドウの下部に CSV ファイルを開くか保存するように求めるメッセージが表示されます。

8. [**名前を付けて保存]** \> をクリックし、CSV ファイルをローカル コンピューター上のフォルダーに保存します。 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>手順 2: PowerQuery エディターを使用してエクスポートされた監査ログを書式設定する

次の手順では、ExcelのPower Query エディターの JSON 変換機能を使用して **、AuditData** 列 (マルチプロパティ JSON オブジェクトで構成される) の各プロパティを独自の列に分割します。 これにより、共有に関連するレコードを表示する列をフィルター処理できます。

詳しい手順については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)」の「手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する」を参照してください。

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>手順 3: 外部ユーザーと共有されているリソースの CSV ファイルをフィルター処理する

次の手順では、「SharePoint共有イベント」セクションで説明した共有関連のさまざまな[イベント](#sharepoint-sharing-events)について CSV をフィルター処理します。 または、 **TargetUserOrGroupType** 列をフィルター処理して、このプロパティの値が **Guest** であるすべてのレコードを表示することもできます。 

前の手順の手順に従って PowerQuery エディターを使用して CSV ファイルを準備したら、次の操作を行います。
    
1. 手順 2. で作成したExcel ファイルを開きます。 

2. [ **ホーム** ] タブで、[ **並べ替え&フィルター**] をクリックし、[ **フィルター**] をクリックします。
    
3. [**操作**] 列 **の [並べ替え&フィルター**] ドロップダウン リストで、すべての選択をクリアし、次の共有関連イベントを 1 つ以上選択して **、[OK]** をクリックします。
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel選択したイベントの行が表示されます。
    
4. **TargetUserOrGroupType** という名前の列に移動し、それを選択します。 
    
5. [ **並べ替え&フィルター** ] ボックスの一覧で、すべての選択をオフにし、 **TargetUserOrGroupType:Guest** を選択して、[OK] をクリック **します**。
    
    これで、外部ユーザーが **TargetUserOrGroupType:Guest** の値で識別されるため、イベントを共有するための行と、ターゲット ユーザーが組織の外部にある行が表示Excel。 
  
> [!TIP]
> 表示される監査レコードの場合、**ObjectId** 列はターゲット ユーザーと共有されたリソースを識別します。たとえば.`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`
