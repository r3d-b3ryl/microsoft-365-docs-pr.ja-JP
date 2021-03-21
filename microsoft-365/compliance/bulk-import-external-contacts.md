---
title: 外部連絡先を Exchange Online に一括インポートする
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
description: 管理者が Exchange Online PowerShell と CSV ファイルを使用して外部連絡先をグローバル アドレス一覧に一括インポートする方法について説明します。
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918213"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="1d220-103">外部連絡先を Exchange Online に一括インポートする</span><span class="sxs-lookup"><span data-stu-id="1d220-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="1d220-104">**この記事は管理者向けです。連絡先を自分のメールボックスにインポートしようとしていますか?「連絡先 [を Outlook にインポートする」を参照してください。](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="1d220-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="1d220-105">Exchange Online の共有アドレス帳 (グローバル アドレス一覧とも呼ばれる) に含める既存のビジネス連絡先が多数存在しますか。</span><span class="sxs-lookup"><span data-stu-id="1d220-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="1d220-106">外部連絡先を、会社内のユーザーと同じ方法で配布グループのメンバーとして追加しますか?</span><span class="sxs-lookup"><span data-stu-id="1d220-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="1d220-107">その場合は、Exchange Online PowerShell と CSV (コンマ区切り値) ファイルを使用して、外部連絡先を Exchange Online に一括インポートできます。</span><span class="sxs-lookup"><span data-stu-id="1d220-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="1d220-108">これは 3 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1d220-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="1d220-109">手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="1d220-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="1d220-110">手順 2: PowerShell を使用して外部連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1d220-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="1d220-111">手順 3: 外部連絡先のプロパティに情報を追加する</span><span class="sxs-lookup"><span data-stu-id="1d220-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="1d220-112">連絡先をインポートするには、次の手順を完了したら、次の追加タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="1d220-113">外部連絡先の追加</span><span class="sxs-lookup"><span data-stu-id="1d220-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="1d220-114">共有アドレス帳から外部連絡先を非表示にする</span><span class="sxs-lookup"><span data-stu-id="1d220-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="1d220-115">手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="1d220-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="1d220-116">最初の手順は、Exchange Online にインポートする各外部連絡先に関する情報を含む CSV ファイルを作成することです。</span><span class="sxs-lookup"><span data-stu-id="1d220-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="1d220-117">次のテキストを NotePad のテキスト ファイルにコピーし、デスクトップに .csv というファイル名のサフィックスを使用して CSV ファイルとして保存します。たとえば、ExternalContacts.csv。</span><span class="sxs-lookup"><span data-stu-id="1d220-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1d220-118">言語に特殊文字 (スウェーデン語の å、ä、öなど) が含まれている場合は、メモパッドにファイルを保存するときに、csv ファイルを UTF-8 または他の Unicode エンコードで保存します。  </span><span class="sxs-lookup"><span data-stu-id="1d220-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="1d220-119">CSV ファイルの最初の行 (ヘッダー行) には、Exchange Online にインポートするときに使用できる連絡先のプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d220-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="1d220-120">各プロパティ名はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="1d220-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="1d220-121">ヘッダー行の下の各行は、1 つの外部連絡先をインポートするプロパティ値を表します。</span><span class="sxs-lookup"><span data-stu-id="1d220-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1d220-122">このテキストには、削除できるサンプル データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d220-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="1d220-123">ただし、最初の (ヘッダー) 行を削除または変更しない。</span><span class="sxs-lookup"><span data-stu-id="1d220-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="1d220-124">外部連絡先のすべてのプロパティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="1d220-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="1d220-125">Excel を使用して CSV ファイルを編集する方がずっと簡単なので、Excel で CSV ファイルを開き、CSV ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="1d220-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="1d220-126">Exchange Online にインポートする連絡先ごとに行を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d220-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="1d220-127">可能な限り多くのセルを設定します。</span><span class="sxs-lookup"><span data-stu-id="1d220-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="1d220-128">この情報は、連絡先ごとに共有アドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d220-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="1d220-129">外部連絡先を作成するには、次のプロパティ (ヘッダー行の最初の 4 つの項目) が必要であり、CSV ファイルに入力する必要があります。 **ExternalEmailAddress**、 **Name**、 **FirstName**、 **LastName**。</span><span class="sxs-lookup"><span data-stu-id="1d220-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="1d220-130">手順 2 で実行する PowerShell コマンドは、これらのプロパティの値を使用して連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d220-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="1d220-131">手順 2: PowerShell を使用して外部連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1d220-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="1d220-132">次の手順では、手順 1 と PowerShell で作成した CSV ファイルを使用して、CSV ファイルに一覧表示されている外部連絡先を Exchange Online に一括インポートします。</span><span class="sxs-lookup"><span data-stu-id="1d220-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="1d220-133">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="1d220-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="1d220-134">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1d220-135">Exchange Online PowerShell に接続する場合は、グローバル管理者アカウントのユーザー名とパスワードを必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="1d220-136">PowerShell を Exchange Online に接続した後、手順 1 で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="1d220-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="1d220-137">次のコマンドを実行して、外部連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="1d220-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="1d220-138">インポートする数によっては、新しい連絡先の作成に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d220-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="1d220-139">コマンドの実行が完了すると、作成された新しい連絡先の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d220-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="1d220-140">新しい外部連絡先を表示するには、Exchange 管理センター (EAC) に移動し、[受信者の連絡先] **を** \> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d220-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="1d220-141">EAC に接続する手順については [、「Exchange Online の Exchange 管理センター」を参照してください](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="1d220-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="1d220-142">必要に応じて、[ **更新]** をクリックしてリストを更新し、インポートされた外部連絡先を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d220-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="1d220-143">インポートされた連絡先は、Outlook と Outlook on the web の共有アドレス帳に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d220-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1d220-144">[ユーザーの連絡先] に移動して、Microsoft 365 管理センターで連絡先 **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="1d220-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="1d220-145">手順 3: 外部連絡先のプロパティに情報を追加する</span><span class="sxs-lookup"><span data-stu-id="1d220-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="1d220-146">手順 2 でコマンドを実行すると、外部連絡先が作成されますが、連絡先または組織の情報 (CSV ファイル内のほとんどのセルからの情報) は含めされません。</span><span class="sxs-lookup"><span data-stu-id="1d220-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="1d220-147">これは、新しい外部連絡先を作成すると、必要なプロパティだけが設定されるためです。</span><span class="sxs-lookup"><span data-stu-id="1d220-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="1d220-148">CSV ファイルにすべての情報が入力されている必要が無い場合は、ご安心ください。</span><span class="sxs-lookup"><span data-stu-id="1d220-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="1d220-149">それがない場合は、追加されません。</span><span class="sxs-lookup"><span data-stu-id="1d220-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="1d220-150">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="1d220-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="1d220-151">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="1d220-152">手順 1 で CSV ファイルを保存したデスクトップ フォルダーに移動します。たとえば、 `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="1d220-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="1d220-153">次の 2 つのコマンドを実行して、CSV ファイルから手順 2 で作成した外部連絡先に他のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="1d220-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="1d220-154">_Manager パラメーターが_ 問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d220-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="1d220-155">CSV ファイル内のセルが空白の場合、エラーが発生し、連絡先にプロパティ情報は追加されません。</span><span class="sxs-lookup"><span data-stu-id="1d220-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="1d220-156">マネージャーを指定する必要がない場合は、前の  ` -Manager $_.Manager ` PowerShell コマンドから削除してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="1d220-157">繰り返しますが、手順 1 でインポートした数に応じて、連絡先の更新に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d220-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="1d220-158">連絡先にプロパティが追加されたと確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d220-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="1d220-159">EAC で、[受信者の連絡先 **] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1d220-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="1d220-160">連絡先をクリックし、[編集 **]** アイコン ![ をクリック ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) して連絡先のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="1d220-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="1d220-161">手順は以上です。</span><span class="sxs-lookup"><span data-stu-id="1d220-161">That's it!</span></span> <span data-ttu-id="1d220-162">ユーザーは、連絡先と追加情報をアドレス帳 Outlook と Outlook on the web で確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="1d220-163">外部連絡先の追加</span><span class="sxs-lookup"><span data-stu-id="1d220-163">Add more external contacts</span></span>

<span data-ttu-id="1d220-164">手順 1 ~ 手順 3 を繰り返して、Exchange Online に新しい外部連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="1d220-165">会社のユーザーは、新しい連絡先の CSV ファイルに新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="1d220-166">次に、手順 2 と手順 3 の PowerShell コマンドを実行して、新しい連絡先に情報を作成して追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d220-167">コマンドを実行して新しい連絡先を作成すると、以前に作成された連絡先が既に存在しているというエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d220-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="1d220-168">ただし、CSV ファイルに追加された新しい連絡先が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d220-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="1d220-169">共有アドレス帳から外部連絡先を非表示></span><span class="sxs-lookup"><span data-stu-id="1d220-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="1d220-170">一部の企業では、外部連絡先のみを使用して、配布グループのメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="1d220-171">このシナリオでは、共有アドレス帳から外部連絡先を非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="1d220-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="1d220-172">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-172">Here's how:</span></span>
  
1.  <span data-ttu-id="1d220-173">PowerShell を Exchange Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="1d220-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="1d220-174">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d220-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="1d220-175">1 つの外部連絡先を非表示にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d220-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="1d220-176">たとえば、共有アドレス帳から Pilar Pinilla を非表示にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d220-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="1d220-177">共有アドレス帳からすべての外部連絡先を非表示にする場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1d220-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="1d220-178">非表示にした後、外部連絡先は共有アドレス帳に表示されませんが、配布グループのメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d220-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>