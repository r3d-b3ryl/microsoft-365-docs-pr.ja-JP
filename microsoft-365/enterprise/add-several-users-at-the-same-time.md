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
ms.openlocfilehash: bb0ed6212cde61693024bcd2fdca9f1d6c3f42dbb063f67324be3d87219f46cf
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53835417"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>複数のユーザーを同時にユーザーに追加する - Microsoft 365 ヘルプ

チームの各ユーザーは、電子メールやメール サービスなどのMicrosoft 365サービスにサインインしてアクセスする前に、ユーザー アカウントをOffice。 ユーザー数が多い場合、Excel のスプレッドシートまたは CSV 形式で保存された他のファイルから、ユーザー アカウントを一括で追加することができます。 [CSV 形式が何か分からず](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?
  
> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>サーバーに複数のユーザーを追加Microsoft 365 管理センター

1. 職場または学校のアカウントを使用して、Microsoft 365 にサインインします。

2. 管理センターで、[**ユーザー**] \> [**アクティブなユーザー**] の順に選択します。

3. [**複数ユーザーの追加**] を選択します。

4. 省略可能ですが、[**複数のユーザーのインポート**] パネルでは、サンプル CSV ファイルをサンプル データ入りまたはなしでダウンロードできます。

    スプレッドシートには、サンプル 1 と **まったく同** じ列見出し (ユーザー名、名など) を含める必要があります。 テンプレートを使用する場合は、メモ帳 のようなテキスト編集ツールでテンプレートを開き、すべてのデータを行 1 に残し、2 行目以下の行にのみデータを入力します。

    スプレッドシートには、各ユーザーのユーザー名 (bob@contoso.com など) と表示名 (Bob Kelly など) の値を含める必要があります。

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. ボックスにファイル パスを入力するか、[**参照**] を選択して CSV ファイルの場所を参照し、[**確認**] を選びます。
  
    ファイルに問題がある場合は、パネルにその問題が表示されます。ログ ファイルをダウンロードすることもできます。

6. [**ユーザー オプションの設定**] ダイアログで、サインイン状態を設定し、すべてのユーザーに割り当てられる製品ライセンスを選択できます。

7. [**結果の表示**] ダイアログで、結果を自分や他のユーザーに送信するかどうかを選択できます (パスワードはプレーン テキストとなります)。作成されたユーザーの数も表示されます。新規ユーザーに割り当てるライセンスを追加購入することもできます。

## <a name="next-steps"></a>次の手順

- これらのユーザーがアカウントを持っているので、PC または Mac で Microsoft 365または Office [2016](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)をダウンロードしてインストールまたは再インストールする必要があります。 チームの各ユーザーは、最大 5 Microsoft 365 Mac にインストールできます。

- 各ユーザーは、iPhone、iPad、Android のスマートフォンやタブレットなどの[モバイル デバイスで Office アプリとメールをセットアップ](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f)でき、最大 5 台のタブレットと 5 台の スマートフォンでセットアップを行えます。 こうすることで、ユーザーはどこからでも Office ファイルを編集できるようになります。

    セットアップ[手順のMicrosoft 365リストについては](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa)、「ビジネス向けアプリケーションのセットアップ」を参照してください。

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>ユーザーをユーザーに追加する方法の詳細Microsoft 365

### <a name="not-sure-what-csv-format-is"></a>CSV 形式とは。

CSV ファイルは、コンマで区切られた値を含むファイルです。 テキスト エディターまたは Excel などのスプレッドシート プログラムを使って、このようなファイルを作成または編集することができます。
  
出発点として、[このサンプル スプレッドシート](https://www.microsoft.com/download/details.aspx?id=45485)をダウンロードして使うことができます。 最初のMicrosoft 365列見出しが必要な場合は、他の行に置き換えないので注意してください。 
  
新しい名前でファイルを保存し、CSV 形式を指定します。
  
![Excel でファイルを CSV 形式で保存する方法を示した画像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
ファイルを保存するときに、CSV 形式でファイルを保存すると、ブックの一部の機能が失われるというメッセージが表示されることがあります。 このメッセージは問題ありません。 [ **はい**] をクリックして続けます。
  
![CSV 形式でファイルを保存するかどうかを確認する Excel メッセージの画像](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>スプレッドシートの書式設定のヒント

- **サンプル スプレッドシートと同じ列見出しにする必要はありますか?** はい。 サンプル スプレッドシートの 1 行目には列見出しが含まれています。 列見出しは必須です。 グループに追加する各ユーザー Microsoft 365、見出しの下に行を作成します。 列見出しを追加、変更、または削除すると、Microsoft 365情報からユーザーを作成できない可能性があります。

- **各ユーザーに必要な情報が揃っていない場合はどのようになりますか?** ユーザー名と表示名は必須で、この情報がないと新しいユーザーは追加できません。FAX 番号などの他の情報が一部欠けている場合は、フィールドが空白であることを示すために、スペースに加えてコンマを使用することができます。

- **スプレッドシートのサイズはどのくらい小さいか大きいか。** スプレッドシートには、少なくとも 2 行が必要です。 One is for the column headings (the user data column label) and one for the user. You cannot have more than 251 rows. If you need to import more than 250 users, you can create more than one spreadsheet.

- **使用できる言語** スプレッドシートを作成するときに、任意の言語または文字でユーザー データ列ラベルを入力できますが、サンプルに示すようにラベルの順序を変更することはできません。 You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.

- **異なる国や地域のユーザーを追加する場合はどうですか?** 領域ごとに別のスプレッドシートを作成します。 スプレッドシートごとにユーザーの一括追加ウィザードの手順を実行し、処理中のファイルに含まれるすべてのユーザーを 1 つの場所にまとめるようにします。

- **使用できる文字数に制限はありますか?** 次の表は、サンプルのスプレッドシート内のユーザーデータの列ラベルと、それぞれの最大文字数を示しています。

|**ユーザー データの 列 ラベル**|**最大文字数**|
|:-----|:-----|
|ユーザー名 (必須)  <br/> |at 記号 (@) を含む 79 の形式 \<extension\> name@domain。 ユーザーのエイリアスは 50 文字を超えることはできません。ドメイン名は 48 文字を超えることはできません。  <br/> |
|名  <br/> |64  <br/> |
|姓  <br/> |64  <br/> |
|表示名 (必須)  <br/> |256  <br/> |
|役職  <br/> |64  <br/> |
|部署  <br/> |64  <br/> |
|事務所番号  <br/> |128  <br/> |
|会社電話  <br/> |64  <br/> |
|携帯電話  <br/> |64  <br/> |
|FAX  <br/> |64  <br/> |
|番地  <br/> |1023  <br/> |
|市区町村  <br/> |128  <br/> |
|都道府県  <br/> |128  <br/> |
|郵便番号  <br/> |40  <br/> |
|国または地域  <br/> |128  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>ユーザーをユーザーに追加するときに問題がMicrosoft 365?

- **スプレッドシートの形式が正しいかどうか慎重にチェックしてください。** サンプル ファイル内の見出しと一致しているか、列見出しをチェックします。文字数の制限に従い、各フィールドがカンマで区切られるようにします。

- **ユーザーに新しいユーザーが表示Microsoft 365、数分待ちます。** 変更がすべてのサービスに適用されるのに少し時間Microsoft 365。 

## <a name="related-articles"></a>関連記事

[ユーザーを個別または一括でユーザーに追加Microsoft 365](/office365/admin/add-users/add-users)