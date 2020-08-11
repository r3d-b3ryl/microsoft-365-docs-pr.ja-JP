---
title: 'コンテンツの理解を設定する (プレビュー) '
description: プロジェクト Cortex をセットアップする方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612704"
---
# <a name="set-up-content-understanding-preview"></a>コンテンツの理解を設定する (プレビュー)

> [!Note] 
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

管理者は、Microsoft 365 管理センターを使用して、コンテンツの理解を設定し、構成することができます。 

セットアップの前に、環境内のコンテンツの理解を設定して構成するための最善の方法を計画してください。 たとえば、次の点について考慮する必要があります。
- どの SharePoint サイトでフォーム処理を有効にしますか? すべてのサイト、一部、またはサイトの選択
- コンテンツセンターの名前、およびプライマリサイト管理者は誰ですか。

管理者は、コンテンツのセットアップ後に、選択した設定を変更して、Microsoft 365 管理センターの管理設定を理解することもできます。


## <a name="requirements"></a>Requirements 
Microsoft 365 管理センターにアクセスし、コンテンツの理解を設定するには、グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。


## <a name="to-set-up-content-understanding"></a>コンテンツの理解を設定するには

1. Microsoft 365 管理センターで、[**セットアップ**] を選択し、[**組織ナレッジ**] セクションを表示します。
2. [**組織ナレッジ**] セクションで、[**コンテンツの理解を自動化**する] を選択します。<br/>

    ![組織ナレッジの設定ページ](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. [**コンテンツを自動的に理解**する] ページで、[**開始**] をクリックして、セットアッププロセスを案内します。<br/>

    ![セットアップの開始](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. [**フォーム処理の構成**] ページで、ユーザーが AI ビルダーを使用して、特定の SharePoint ドキュメントライブラリのフォーム処理モデルを作成できるようにするかどうかを選択できます。 [ドキュメントライブラリ] リボンでメニューオプションを使用して、フォーム処理モデルが有効になっている SharePoint ドキュメントライブラリに**フォーム処理モデルを作成**できます。
 
     **フォーム処理モデルを作成するためのオプションをどの SharePoint ライブラリに表示するかを指定**するには、次のオプションを選択します。</br>
    - テナント内のすべての SharePoint ライブラリで利用できるようにするための**すべての sharepoint ライブラリ**。</br>
    - [**選択したサイトのライブラリのみ**] を選択し、使用できるようにするサイトを選択します。</br>
    - 現在、どのサイトでも使用できるようにしない場合は、 **SharePoint ライブラリはありません**(セットアップ後に変更できます)。
</br>

   ![フォーム処理を構成する](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > SharePoint ドキュメントライブラリでこの設定を有効にしても、ライブラリに適用されている既存のモデル、またはドキュメントを認識するモデルをライブラリに適用する機能には影響しません。 

    
5. [**コンテンツセンターの作成**] ページで、ユーザーがドキュメントを作成および管理できる SharePoint コンテンツセンターサイトを作成できます。 </br>
    a. [**サイト名**] に、コンテンツセンターサイトに付ける名前を入力します。</br>
    b. サイト**アドレス**には、サイト名に対して選択した内容に基づいてサイトの URL が表示されます。</br>

    > [!Note] 
    > サポートされている言語を選択することはできますが、モデルを理解しているのは英語版のコンテンツのみを作成できることに注意してください。</br>

      ![コンテンツセンターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>


    [**次へ**] を選択します。
6. [**完了と確認**] ページで、選択した設定を確認して、変更を行うことができます。 選択内容に問題がなければ、[**アクティブ化**] を選択します。



7. コンテンツを理解すると、**アクティブ化**されたページが表示され、システムがフォーム処理の設定を追加し、コンテンツセンターサイトを作成したことを確認できます。 [**完了**] を選択します。

8. **コンテンツの自動理解**ページに戻ります。 このページでは、[**管理**] を選択して構成設定に変更を加えることができます。 

## <a name="see-also"></a>関連項目



  






