---
title: 外部連絡先をExchange Onlineに一括インポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
ms.custom: admindeeplinkEXCHANGE
description: 管理者が powerShell と CSV ファイルExchange Online使用して、外部連絡先をグローバル アドレス一覧に一括インポートする方法について説明します。
ms.openlocfilehash: a85d24a4b20798df057250d9114f97563a6a8e2d
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64999302"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>外部連絡先をExchange Onlineに一括インポートする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**この記事は管理者向けです。連絡先を自分のメールボックスにインポートしようとしていますか?Outlook [への連絡先のインポートに関する](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)Outlook**
   
会社には、Exchange Onlineの共有アドレス帳 (グローバル アドレス一覧とも呼ばれます) に含める既存のビジネス連絡先が多数存在しますか? 社内のユーザーと同様に、外部連絡先を配布グループのメンバーとして追加しますか? その場合は、Exchange Online PowerShell と CSV (コンマ区切り値) ファイルを使用して、外部連絡先をExchange Onlineに一括インポートできます。 これは 3 段階のプロセスです。
  
[手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[手順 2: PowerShell を使用して外部連絡先を作成する](#step-2-create-the-external-contacts-with-powershell) 

[手順 3: 外部連絡先のプロパティに情報を追加する](#step-3-add-information-to-the-properties-of-the-external-contacts)

連絡先をインポートする手順を完了したら、次の追加タスクを実行できます。
  
- [外部連絡先をさらに追加する](#add-more-external-contacts)
  
- [共有アドレス帳から外部連絡先を非表示にする](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する

最初の手順では、Exchange Onlineにインポートする各外部連絡先に関する情報を含む CSV ファイルを作成します。 
  
1. 次のテキストを NotePad のテキスト ファイルにコピーし、.csv のファイル名サフィックスを使用してデスクトップに CSV ファイルとして保存します。たとえば、ExternalContacts.csv。
    
    > [!TIP]
    > 言語に特殊文字 (スウェーデン語の **å**、 **ä**、 **ö** など) が含まれている場合は、NotePad でファイルを保存するときに、UTF-8 またはその他の Unicode エンコードで CSV ファイルを保存します。 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    CSV ファイルの最初の行 (ヘッダー行) には、Exchange Onlineにインポートするときに使用できる連絡先のプロパティが一覧表示されます。 各プロパティ名はコンマで区切られます。 ヘッダー行の下の各行は、1 つの外部連絡先をインポートするためのプロパティ値を表します。 
    
    > [!NOTE]
    > このテキストには、削除できるサンプル データが含まれています。 ただし、最初の (ヘッダー) 行は削除または変更しないでください。 外部連絡先のすべてのプロパティが含まれています。 
  
2. Microsoft Excelで CSV ファイルを開いて CSV ファイルを編集する方法は、Excelを使用して CSV ファイルを編集する方がはるかに簡単であるためです。
    
3. Exchange Onlineにインポートする連絡先ごとに行を作成します。 できるだけ多くのセルを設定します。 この情報は、各連絡先の共有アドレス帳に表示されます。 
    
    > [!IMPORTANT]
    >  外部連絡先を作成するには、次のプロパティ (ヘッダー行の最初の 4 つの項目) が必要であり、CSV ファイルに **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName** を入力する必要があります。 手順 2 で実行する PowerShell コマンドは、これらのプロパティの値を使用して連絡先を作成します。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>手順 2: PowerShell を使用して外部連絡先を作成する

次の手順では、手順 1 と PowerShell で作成した CSV ファイルを使用して、CSV ファイルに一覧表示されている外部連絡先をExchange Onlineに一括インポートします。 
  
1.  PowerShell をExchange Online組織にConnectします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 PowerShell に接続するときは、必ずグローバル管理者アカウントのユーザー名とパスワードExchange Online使用してください。 
    
2. PowerShell をExchange Onlineに接続した後、手順 1. で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば`C:\Users\Administrator\desktop`、
    
3. 次のコマンドを実行して、外部連絡先を作成します。

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    インポートする連絡先の数によっては、新しい連絡先の作成に時間がかかる場合があります。 コマンドの実行が完了すると、作成された新しい連絡先の一覧が PowerShell に表示されます。 
    
4. 新しい外部連絡先を表示するには、Exchange管理センター (EAC) に移動し、[**受信者の** \> <a href="https://go.microsoft.com/fwlink/?linkid=2182970" target="_blank">**連絡先**</a>] をクリックします。 
    
    > [!TIP]
    > EAC に接続する手順については、[Exchange Onlineの管理センター Exchange](/exchange/exchange-admin-center)参照してください。 
  
5. 必要に応じて、[ **更新]** をクリックしてリストを更新し、インポートされた外部連絡先を表示します。 
    
    インポートされた連絡先は、OutlookとOutlook on the webの共有アドレス帳に表示されます。
    
    > [!NOTE]
    > [**ユーザー**\>の連絡先] に移動して、Microsoft 365 管理センターの **連絡先** を表示することもできます。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>手順 3: 外部連絡先のプロパティに情報を追加する

手順 2 でコマンドを実行すると、外部連絡先は作成されますが、連絡先や組織の情報は含まれません。これは、CSV ファイル内のほとんどのセルからの情報です。 これは、新しい外部連絡先を作成するときに、必要なプロパティのみが設定されるためです。 CSV ファイルにすべての情報が入力されていない場合は、心配しないでください。 存在しない場合は、追加されません。
  
1.  PowerShell をExchange Online組織にConnectします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。
    
2. 手順 1 で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば、. `C:\Users\Administrator\desktop`
    
3. 次の 2 つのコマンドを実行して、CSV ファイルの他のプロパティを、手順 2. で作成した外部連絡先に追加します。
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_ パラメーターが問題になる可能性があります。 CSV ファイル内のセルが空白の場合、エラーが発生し、連絡先にプロパティ情報は追加されません。 マネージャーを指定する必要がない場合は、前の PowerShell コマンドから削除  ` -Manager $_.Manager ` するだけです。 
  
    ここでも、手順 1 でインポートした数によっては、連絡先の更新に時間がかかる場合があります。 
    
4. プロパティが連絡先に追加されたことを確認するには、 
    
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>で、[**受信者の**\>連絡先] に移動 **します**。
    
2. 連絡先をクリックし、[ **編集]** ![アイコンをクリックします。](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) をクリックすると、連絡先のプロパティが表示されます。 
    
手順は以上です。 ユーザーは、アドレス帳のOutlookとOutlook on the webで連絡先と追加情報を確認できます。
  
## <a name="add-more-external-contacts"></a>外部連絡先をさらに追加する

手順 1 ~ 手順 3 を繰り返して、Exchange Onlineに新しい外部連絡先を追加できます。 会社のユーザーは、新しい連絡先の CSV ファイルに新しい行を追加できます。 次に、手順 2 と手順 3 の PowerShell コマンドを実行して、新しい連絡先に情報を作成して追加できます。
  
> [!NOTE]
> コマンドを実行して新しい連絡先を作成すると、以前に作成された連絡先が既に存在するというエラーが表示される場合があります。 ただし、CSV ファイルに追加された新しい連絡先は作成されます。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>共有アドレス帳>から外部連絡先を非表示にする

一部の企業では、外部連絡先を配布グループのメンバーとして追加できるようにのみ使用できます。 このシナリオでは、共有アドレス帳から外部連絡先を非表示にすることができます。 次の操作を実行してください。
  
1.  PowerShell をExchange Online組織にConnectします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。
    
2. 1 つの外部連絡先を非表示にするには、次のコマンドを実行します。
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    たとえば、共有アドレス帳から Pilar Pinilla を非表示にするには、次のコマンドを実行します。

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. 共有アドレス帳からすべての外部連絡先を非表示にするには、次のコマンドを実行します。

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

非表示にすると、共有アドレス帳に外部連絡先は表示されませんが、配布グループのメンバーとして追加することはできます。