---
title: 外部連絡先を連絡先に一括インポートExchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 管理者が PowerShell と CSV Exchange Onlineを使用して、外部連絡先をグローバル アドレス一覧に一括インポートする方法について説明します。
ms.openlocfilehash: 8f4b9dc36a591081bd19fb2661cf95ef6ea6d91c
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58565430"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>外部連絡先を連絡先に一括インポートExchange Online

**この記事は管理者向けです。連絡先を自分のメールボックスにインポートしようとしていますか?「連絡先 [を連絡先にインポートする」を参照Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
会社には、共有アドレス帳 (グローバル アドレス一覧とも呼ばれる) に含める既存のビジネス連絡先が多数Exchange Online。 外部連絡先を、会社内のユーザーと同じ方法で配布グループのメンバーとして追加しますか? その場合は、PowerShell Exchange Online CSV (コンマ区切り値) ファイルを使用して、外部連絡先を外部連絡先に一括インポートExchange Online。 これは 3 段階のプロセスです。
  
[手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[手順 2: PowerShell を使用して外部連絡先を作成する](#step-2-create-the-external-contacts-with-powershell) 

[手順 3: 外部連絡先のプロパティに情報を追加する](#step-3-add-information-to-the-properties-of-the-external-contacts)

連絡先をインポートするには、次の手順を完了したら、次の追加タスクを実行できます。
  
- [外部連絡先の追加](#add-more-external-contacts)
  
- [共有アドレス帳から外部連絡先を非表示にする](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する

最初の手順は、インポートする各外部連絡先に関する情報を含む CSV ファイルを作成Exchange Online。 
  
1. 次のテキストを NotePad のテキスト ファイルにコピーし、デスクトップに CSV ファイルとして保存するには、ファイル名のサフィックスを使用.csv。たとえば、ExternalContacts.csv。
    
    > [!TIP]
    > 言語に特殊文字 (スウェーデン語の å、ä、öなど) が含まれている場合は、メモパッドにファイルを保存するときに、csv ファイルを UTF-8 または他の Unicode エンコードで保存します。   
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    CSV ファイルの最初の行 (ヘッダー行) には、連絡先をインポートするときに使用できる連絡先のプロパティExchange Online。 各プロパティ名はコンマで区切られます。 ヘッダー行の下の各行は、1 つの外部連絡先をインポートするプロパティ値を表します。 
    
    > [!NOTE]
    > このテキストには、削除できるサンプル データが含まれています。 ただし、最初の (ヘッダー) 行を削除または変更しない。 外部連絡先のすべてのプロパティが含まれる。 
  
2. CSV ファイルを編集するには、Microsoft Excelファイルを編集する方がずっと簡単なので、Excel CSV ファイルを開きます。
    
3. インポート先の連絡先ごとに行を作成Exchange Online。 可能な限り多くのセルを設定します。 この情報は、連絡先ごとに共有アドレス帳に表示されます。 
    
    > [!IMPORTANT]
    >  外部連絡先を作成するには、次のプロパティ (ヘッダー行の最初の 4 つの項目) が必要であり、CSV ファイルに入力する必要があります。 **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName**。 手順 2 で実行する PowerShell コマンドは、これらのプロパティの値を使用して連絡先を作成します。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>手順 2: PowerShell を使用して外部連絡先を作成する

次の手順では、手順 1 と PowerShell で作成した CSV ファイルを使用して、CSV ファイルに一覧表示されている外部連絡先を一括インポートExchange Online。 
  
1.  ConnectPowerShell を組織Exchange Onlineします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 PowerShell に接続する場合は、グローバル管理者アカウントのユーザー名とパスワードExchange Onlineしてください。 
    
2. PowerShell をデバイス に接続Exchange Online、手順 1 で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば `C:\Users\Administrator\desktop` .
    
3. 次のコマンドを実行して、外部連絡先を作成します。

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    インポートする数によっては、新しい連絡先の作成に時間がかかる場合があります。 コマンドの実行が完了すると、作成された新しい連絡先の一覧が表示されます。 
    
4. 新しい外部連絡先を表示するには、管理センター (EAC) Exchangeに移動し、[受信者の連絡先]**を** \> **クリックします**。 
    
    > [!TIP]
    > EAC に接続する手順については、「Exchange[管理センター」を参照Exchange Online。](/exchange/exchange-admin-center) 
  
5. 必要に応じて、[ **更新]** をクリックしてリストを更新し、インポートされた外部連絡先を確認します。 
    
    インポートされた連絡先は、共有アドレス帳の [連絡先] および [連絡先] OutlookにOutlook on the web。
    
    > [!NOTE]
    > [ユーザーの連絡先] にアクセスして、Microsoft 365 管理センター連絡先を **表示** \> **できます**。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>手順 3: 外部連絡先のプロパティに情報を追加する

手順 2 でコマンドを実行すると、外部連絡先が作成されますが、連絡先または組織の情報 (CSV ファイル内のほとんどのセルからの情報) は含めされません。 これは、新しい外部連絡先を作成すると、必要なプロパティだけが設定されるためです。 CSV ファイルにすべての情報が入力されている必要が無い場合は、ご安心ください。 それがない場合は、追加されません。
  
1.  ConnectPowerShell を組織Exchange Onlineします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。
    
2. 手順 1 で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば、 `C:\Users\Administrator\desktop` .
    
3. 次の 2 つのコマンドを実行して、CSV ファイルから手順 2 で作成した外部連絡先に他のプロパティを追加します。
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager パラメーターが_ 問題になる可能性があります。 CSV ファイル内のセルが空白の場合、エラーが発生し、連絡先にプロパティ情報は追加されません。 マネージャーを指定する必要がない場合は、前の  ` -Manager $_.Manager ` PowerShell コマンドから削除してください。 
  
    繰り返しますが、手順 1 でインポートした数に応じて、連絡先の更新に時間がかかる場合があります。 
    
4. 連絡先にプロパティが追加されたと確認するには、次の手順を実行します。 
    
1. EAC で、[受信者の連絡先 **] に** \> **移動します**。
    
2. 連絡先をクリックし、[編集] **アイコンを** ![ クリックします。](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) をクリックして連絡先のプロパティを表示します。 
    
手順は以上です。 ユーザーは、連絡先と追加情報をアドレス帳のアドレス帳に表示Outlook、Outlook on the web。
  
## <a name="add-more-external-contacts"></a>外部連絡先の追加

手順 1 ~ 手順 3 を繰り返して、新しい外部連絡先を追加Exchange Online。 会社のユーザーは、新しい連絡先の CSV ファイルに新しい行を追加できます。 次に、手順 2 と手順 3 の PowerShell コマンドを実行して、新しい連絡先に情報を作成して追加できます。
  
> [!NOTE]
> コマンドを実行して新しい連絡先を作成すると、以前に作成された連絡先が既に存在しているというエラーが表示される場合があります。 ただし、CSV ファイルに追加された新しい連絡先が作成されます。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>共有アドレス帳から外部連絡先を非表示>

一部の企業では、外部連絡先のみを使用して、配布グループのメンバーとして追加できます。 このシナリオでは、共有アドレス帳から外部連絡先を非表示にできます。 次の操作を実行してください。
  
1.  ConnectPowerShell を組織Exchange Onlineします。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。
    
2. 1 つの外部連絡先を非表示にするには、次のコマンドを実行します。
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    たとえば、共有アドレス帳から Pilar Pinilla を非表示にする場合は、次のコマンドを実行します。

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. 共有アドレス帳からすべての外部連絡先を非表示にする場合は、次のコマンドを実行します。

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

非表示にした後、外部連絡先は共有アドレス帳に表示されませんが、配布グループのメンバーとして追加できます。