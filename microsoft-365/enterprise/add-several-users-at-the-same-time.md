---
title: 複数のユーザーを同時にユーザーに追加する - Microsoft 365 ヘルプ
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'スプレッドシートまたは他の CSV 形式のファイルMicrosoft 365リストから複数のユーザーをビジネス用に追加する方法について説明します。 YouTube で、アカウントをユーザーに追加する方法を説明するビデオをMicrosoft 365。 このプロセスの最後に、アカウントを持つ各ユーザーにメールボックスがMicrosoft 365されます。 '
ms.openlocfilehash: 6b3e8d885466e44a4aa23427a54cfc98b2eebdf3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905622"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="6136b-105">複数のユーザーを同時にユーザーに追加する - Microsoft 365 ヘルプ</span><span class="sxs-lookup"><span data-stu-id="6136b-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="6136b-106">チームの各ユーザーは、電子メールやメール サービスなどのMicrosoft 365サービスにサインインしてアクセスする前に、ユーザー アカウントをOffice。</span><span class="sxs-lookup"><span data-stu-id="6136b-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="6136b-107">ユーザー数が多い場合、Excel のスプレッドシートまたは CSV 形式で保存された他のファイルから、ユーザー アカウントを一括で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6136b-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> <span data-ttu-id="6136b-108">[CSV 形式が何か分からず](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span><span class="sxs-lookup"><span data-stu-id="6136b-108">[Not sure what CSV format is](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span></span>
  
> [!NOTE]
> <span data-ttu-id="6136b-109">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6136b-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6136b-110">管理センターに複数のユーザーをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="6136b-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="6136b-111">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6136b-111">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="6136b-112">管理センターで、[**ユーザー**] \> [**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6136b-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="6136b-113">[**複数ユーザーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6136b-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="6136b-114">省略可能ですが、[**複数のユーザーのインポート**] パネルでは、サンプル CSV ファイルをサンプル データ入りまたはなしでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6136b-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span>

    <span data-ttu-id="6136b-115">スプレッドシートには、サンプル 1 と **まったく同** じ列見出し (ユーザー名、名など) を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6136b-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="6136b-116">テンプレートを使用する場合は、メモ帳 のようなテキスト編集ツールでテンプレートを開き、すべてのデータを行 1 に残し、2 行目以下の行にのみデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="6136b-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span>

    <span data-ttu-id="6136b-117">スプレッドシートには、各ユーザーのユーザー名 (bob@contoso.com など) と表示名 (Bob Kelly など) の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6136b-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span>

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="6136b-118">ボックスにファイル パスを入力するか、[**参照**] を選択して CSV ファイルの場所を参照し、[**確認**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6136b-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="6136b-p104">ファイルに問題がある場合は、パネルにその問題が表示されます。ログ ファイルをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6136b-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>

6. <span data-ttu-id="6136b-121">[**ユーザー オプションの設定**] ダイアログで、サインイン状態を設定し、すべてのユーザーに割り当てられる製品ライセンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6136b-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span>

7. <span data-ttu-id="6136b-122">[**結果の表示**] ダイアログで、結果を自分や他のユーザーに送信するかどうかを選択できます (パスワードはプレーン テキストとなります)。作成されたユーザーの数も表示されます。新規ユーザーに割り当てるライセンスを追加購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="6136b-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6136b-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="6136b-123">Next steps</span></span>

- <span data-ttu-id="6136b-124">これらのユーザーがアカウントを持っているので、PC または Mac で Microsoft 365または Office [2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)をダウンロードしてインストールまたは再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6136b-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="6136b-125">チームの各ユーザーは、最大 5 Microsoft 365 Mac にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6136b-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span>

- <span data-ttu-id="6136b-126">各ユーザーは、iPhone、iPad、Android のスマートフォンやタブレットなどの[モバイル デバイスで Office アプリとメールをセットアップ](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f)でき、最大 5 台のタブレットと 5 台の スマートフォンでセットアップを行えます。</span><span class="sxs-lookup"><span data-stu-id="6136b-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="6136b-127">こうすることで、ユーザーはどこからでも Office ファイルを編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6136b-127">This way they can edit Office files from anywhere.</span></span>

    <span data-ttu-id="6136b-128">セットアップ[手順のMicrosoft 365リストについては](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa)、「ビジネス向けアプリケーションのセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6136b-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span>

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="6136b-129">ユーザーをユーザーに追加する方法の詳細Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6136b-129">More information about how to add users to Microsoft 365</span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="6136b-130">CSV 形式とは。</span><span class="sxs-lookup"><span data-stu-id="6136b-130">Not sure what CSV format is?</span></span>

<span data-ttu-id="6136b-p107">CSV ファイルは、コンマで区切られた値を含むファイルです。 テキスト エディターまたは Excel などのスプレッドシート プログラムを使って、このようなファイルを作成または編集することができます。</span><span class="sxs-lookup"><span data-stu-id="6136b-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="6136b-133">出発点として、[このサンプル スプレッドシート](https://www.microsoft.com/download/details.aspx?id=45485)をダウンロードして使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6136b-133">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="6136b-134">最初のMicrosoft 365列見出しが必要な場合は、他の行に置き換えないので注意してください。</span><span class="sxs-lookup"><span data-stu-id="6136b-134">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="6136b-135">新しい名前でファイルを保存し、CSV 形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="6136b-135">Save the file with a new name, and specify CSV format.</span></span>
  
![Excel でファイルを CSV 形式で保存する方法を示した画像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="6136b-p109">ファイルを保存するときに、CSV 形式でファイルを保存すると、ブックの一部の機能が失われるというメッセージが表示されることがあります。 このメッセージは問題ありません。 [ **はい**] をクリックして続けます。</span><span class="sxs-lookup"><span data-stu-id="6136b-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span>
  
![CSV 形式でファイルを保存するかどうかを確認する Excel メッセージの画像](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="6136b-141">スプレッドシートの書式設定のヒント</span><span class="sxs-lookup"><span data-stu-id="6136b-141">Tips for formatting your spreadsheet</span></span>

- <span data-ttu-id="6136b-142">**サンプル スプレッドシートと同じ列見出しにする必要はありますか?**</span><span class="sxs-lookup"><span data-stu-id="6136b-142">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="6136b-143">はい。</span><span class="sxs-lookup"><span data-stu-id="6136b-143">Yes.</span></span> <span data-ttu-id="6136b-144">サンプル スプレッドシートの 1 行目には列見出しが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6136b-144">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="6136b-145">列見出しは必須です。</span><span class="sxs-lookup"><span data-stu-id="6136b-145">These headings are required.</span></span> <span data-ttu-id="6136b-146">グループに追加する各ユーザー Microsoft 365、見出しの下に行を作成します。</span><span class="sxs-lookup"><span data-stu-id="6136b-146">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="6136b-147">列見出しを追加、変更、または削除すると、Microsoft 365情報からユーザーを作成できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6136b-147">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span>

- <span data-ttu-id="6136b-p111">**各ユーザーに必要な情報が揃っていない場合はどのようになりますか?** ユーザー名と表示名は必須で、この情報がないと新しいユーザーは追加できません。FAX 番号などの他の情報が一部欠けている場合は、フィールドが空白であることを示すために、スペースに加えてコンマを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6136b-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span>

- <span data-ttu-id="6136b-151">**スプレッドシートのサイズはどのくらい小さいか大きいか。**</span><span class="sxs-lookup"><span data-stu-id="6136b-151">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="6136b-152">スプレッドシートには、少なくとも 2 行が必要です。</span><span class="sxs-lookup"><span data-stu-id="6136b-152">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="6136b-153">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="6136b-153">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="6136b-154">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="6136b-154">You cannot have more than 251 rows.</span></span> <span data-ttu-id="6136b-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="6136b-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span>

- <span data-ttu-id="6136b-156">**使用できる言語**</span><span class="sxs-lookup"><span data-stu-id="6136b-156">**What languages can I use?**</span></span> <span data-ttu-id="6136b-157">スプレッドシートを作成するときに、任意の言語または文字でユーザー データ列ラベルを入力できますが、サンプルに示すようにラベルの順序を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6136b-157">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="6136b-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="6136b-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span>

- <span data-ttu-id="6136b-p114">**異なる国や地域のユーザーを追加する場合はどうですか?** 領域ごとに別のスプレッドシートを作成します。 スプレッドシートごとにユーザーの一括追加ウィザードの手順を実行し、処理中のファイルに含まれるすべてのユーザーを 1 つの場所にまとめるようにします。</span><span class="sxs-lookup"><span data-stu-id="6136b-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span>

- <span data-ttu-id="6136b-p115">**使用できる文字数に制限はありますか?** 次の表は、サンプルのスプレッドシート内のユーザーデータの列ラベルと、それぞれの最大文字数を示しています。</span><span class="sxs-lookup"><span data-stu-id="6136b-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span>

|<span data-ttu-id="6136b-164">**ユーザー データの 列 ラベル**</span><span class="sxs-lookup"><span data-stu-id="6136b-164">**User data column label**</span></span>|<span data-ttu-id="6136b-165">**最大文字数**</span><span class="sxs-lookup"><span data-stu-id="6136b-165">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6136b-166">ユーザー名 (必須)</span><span class="sxs-lookup"><span data-stu-id="6136b-166">User Name (Required)</span></span>  <br/> |<span data-ttu-id="6136b-167">at 記号 (@) を含む 79 の形式 \<extension\> name@domain。</span><span class="sxs-lookup"><span data-stu-id="6136b-167">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="6136b-168">ユーザーのエイリアスは 50 文字を超えることはできません。ドメイン名は 48 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="6136b-168">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="6136b-169">名</span><span class="sxs-lookup"><span data-stu-id="6136b-169">First Name</span></span>  <br/> |<span data-ttu-id="6136b-170">64</span><span class="sxs-lookup"><span data-stu-id="6136b-170">64</span></span>  <br/> |
|<span data-ttu-id="6136b-171">姓</span><span class="sxs-lookup"><span data-stu-id="6136b-171">Last Name</span></span>  <br/> |<span data-ttu-id="6136b-172">64</span><span class="sxs-lookup"><span data-stu-id="6136b-172">64</span></span>  <br/> |
|<span data-ttu-id="6136b-173">表示名 (必須)</span><span class="sxs-lookup"><span data-stu-id="6136b-173">Display Name (required)</span></span>  <br/> |<span data-ttu-id="6136b-174">256</span><span class="sxs-lookup"><span data-stu-id="6136b-174">256</span></span>  <br/> |
|<span data-ttu-id="6136b-175">役職</span><span class="sxs-lookup"><span data-stu-id="6136b-175">Job Title</span></span>  <br/> |<span data-ttu-id="6136b-176">64</span><span class="sxs-lookup"><span data-stu-id="6136b-176">64</span></span>  <br/> |
|<span data-ttu-id="6136b-177">部署</span><span class="sxs-lookup"><span data-stu-id="6136b-177">Department</span></span>  <br/> |<span data-ttu-id="6136b-178">64</span><span class="sxs-lookup"><span data-stu-id="6136b-178">64</span></span>  <br/> |
|<span data-ttu-id="6136b-179">事務所番号</span><span class="sxs-lookup"><span data-stu-id="6136b-179">Office Number</span></span>  <br/> |<span data-ttu-id="6136b-180">128</span><span class="sxs-lookup"><span data-stu-id="6136b-180">128</span></span>  <br/> |
|<span data-ttu-id="6136b-181">会社電話</span><span class="sxs-lookup"><span data-stu-id="6136b-181">Office Phone</span></span>  <br/> |<span data-ttu-id="6136b-182">64</span><span class="sxs-lookup"><span data-stu-id="6136b-182">64</span></span>  <br/> |
|<span data-ttu-id="6136b-183">携帯電話</span><span class="sxs-lookup"><span data-stu-id="6136b-183">Mobile Phone</span></span>  <br/> |<span data-ttu-id="6136b-184">64</span><span class="sxs-lookup"><span data-stu-id="6136b-184">64</span></span>  <br/> |
|<span data-ttu-id="6136b-185">FAX</span><span class="sxs-lookup"><span data-stu-id="6136b-185">Fax</span></span>  <br/> |<span data-ttu-id="6136b-186">64</span><span class="sxs-lookup"><span data-stu-id="6136b-186">64</span></span>  <br/> |
|<span data-ttu-id="6136b-187">番地</span><span class="sxs-lookup"><span data-stu-id="6136b-187">Address</span></span>  <br/> |<span data-ttu-id="6136b-188">1023</span><span class="sxs-lookup"><span data-stu-id="6136b-188">1023</span></span>  <br/> |
|<span data-ttu-id="6136b-189">市区町村</span><span class="sxs-lookup"><span data-stu-id="6136b-189">City</span></span>  <br/> |<span data-ttu-id="6136b-190">128</span><span class="sxs-lookup"><span data-stu-id="6136b-190">128</span></span>  <br/> |
|<span data-ttu-id="6136b-191">都道府県</span><span class="sxs-lookup"><span data-stu-id="6136b-191">State or Province</span></span>  <br/> |<span data-ttu-id="6136b-192">128</span><span class="sxs-lookup"><span data-stu-id="6136b-192">128</span></span>  <br/> |
|<span data-ttu-id="6136b-193">郵便番号</span><span class="sxs-lookup"><span data-stu-id="6136b-193">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="6136b-194">40</span><span class="sxs-lookup"><span data-stu-id="6136b-194">40</span></span>  <br/> |
|<span data-ttu-id="6136b-195">国または地域</span><span class="sxs-lookup"><span data-stu-id="6136b-195">Country or Region</span></span>  <br/> |<span data-ttu-id="6136b-196">128</span><span class="sxs-lookup"><span data-stu-id="6136b-196">128</span></span>  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="6136b-197">ユーザーをユーザーに追加するときに問題がMicrosoft 365?</span><span class="sxs-lookup"><span data-stu-id="6136b-197">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="6136b-p117">**スプレッドシートの形式が正しいかどうか慎重にチェックしてください。** サンプル ファイル内の見出しと一致しているか、列見出しをチェックします。文字数の制限に従い、各フィールドがカンマで区切られるようにします。</span><span class="sxs-lookup"><span data-stu-id="6136b-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span>

- <span data-ttu-id="6136b-201">**ユーザーに新しいユーザーが表示Microsoft 365、数分待ちます。**</span><span class="sxs-lookup"><span data-stu-id="6136b-201">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="6136b-202">変更がすべてのサービスに適用されるのに少し時間Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="6136b-202">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="6136b-203">関連記事</span><span class="sxs-lookup"><span data-stu-id="6136b-203">Related articles</span></span>

[<span data-ttu-id="6136b-204">ユーザーを個別または一括でユーザーに追加Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6136b-204">Add users individually or in bulk to Microsoft 365</span></span>](/office365/admin/add-users/add-users)