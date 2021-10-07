---
title: 組織のテーマをカスタマイズする
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: ナビゲーション バーの上部の既定のテーマを変更し、Microsoft 365ロゴや色に合わせてカスタマイズする方法について学習します。
ms.openlocfilehash: f6aa013d20cfedcc8d61d005e21db11c58cb5f6f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197810"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>組織のMicrosoft 365テーマをカスタマイズする

組織の管理者は、組織内のユーザーに対して複数のテーマを作成し、組織の異なるメンバーに適用するテーマを選択できます。 組織のテーマは、組織内のユーザーのトップ ナビゲーション バーに表示されるテーマです。

組織内のすべてのユーザーに適用される既定のテーマを追加または更新できます。また、複数のグループに割り当て可能な最大 4 つのグループ テーマMicrosoft 365できます。
  
## <a name="add-or-update-your-organizations-theme"></a>組織のテーマを追加または更新する

1. 管理センターで、[組織プロファイル]ページ設定、[組織設定] \> **タブを選択** します。

2. [組織プロファイル **] タブで** 、[カスタム テーマ] **を選択します**。

すべての組織のテーマは、次のタブを使用してカスタマイズできます。

|**Tab**|**What can you do?**|
|:-----|:-----|
|[全般](#general-modify-a-theme) <br/> |テーマ名を変更し、最大 5 つのグループに割り当てる (該当する場合)。  <br/> |
|[ロゴ](#logos-specify-your-theme-logos) <br/> |暗いテーマの代替ロゴを含む組織のロゴを追加します。  <br/> |
|[Colors](#colors-choose-theme-colors) <br/> |ナビゲーション バー、アクセント、テキスト、アイコンの色を指定して配色をカスタマイズします。 <br/> |

## <a name="general-modify-a-theme"></a>全般: テーマを変更する

[全般] タブでのエクスペリエンスは、既定のテーマまたはグループ テーマを追加または変更するかどうかによって異なります。

### <a name="update-the-default-theme"></a>既定のテーマを更新する

既定のテーマは、最初に表示されるテーマです。  

1. 組織のテーマを以前にカスタマイズした場合は、[既定のテーマ] を選択して保存したカスタマイズのいずれかを使用するか、[テーマの追加]**を選択します**。
2. [全般 **] ページ** では、ユーザーがテーマを上書きし、ユーザーの表示名を表示できます。
3. **[保存]** を選び、変更内容を保存します。  

> [!IMPORTANT]
> 既定のテーマは一意であり、名前を変更したり、組織内のすべてのユーザーに適用したりできない。 既定のテーマを削除するには、最初に他のすべてのテーマを削除する必要があります。

:::image type="content" source="../../media/Default_Theme_Panel1.png" alt-text="スクリーンショット: 組織の既定のテーマを示す [全般] タブ":::

### <a name="create-a-group-theme"></a>グループ テーマの作成

最大 4 つの追加のグループ テーマを作成できます。

1. [全般 **] ページ** で、新しいテーマの名前を入力します。

2. [**グループ**] で、既定のテーマを使用Microsoft 365、グループ テーマを表示できる最大 5 つのグループを選択できます。 また、ユーザーがテーマを上書きし、ユーザーの表示名を表示するのを防ぐことも可能です。

3. **[保存]** を選択します。

:::image type="content" source="../../media/default-theme-general-users1.png" alt-text="スクリーンショット: 組織内のユーザーグループの既定のテーマを示す [全般] タブ":::

## <a name="logos-specify-your-theme-logos"></a>ロゴ: テーマのロゴを指定する

[ロゴ **] ページ** では、ロゴを追加し、ユーザーがロゴを選択するときに移動する URL を指定できます。

- **既定のロゴ**: ロゴをポイントする URL の場所を追加します。 URL が HTTPS を使用するようにします。 匿名アクセスを許可し、認証を必要としない HTTPS イメージ URL を追加します。 既定のテーマの場合は、10 kb 未満のロゴ 画像をアップロードすることもできます。 既定のロゴは、JPG、PNG、GIF、または SVG 形式で指定できます。 SVG イメージの場合は、垂直方向に 24 ピクセルに収まるサイズに変更されます。 JPG、PNG、GIF 画像は、200 x 48 ピクセルに合わせて拡大縮小されます。 ロゴの縦横比は常に保持されます。
- **代替ロゴ**: ロゴをポイントする URL の場所を追加します。 代替ロゴは、暗いテーマで使用Officeする必要があります。 既定のロゴと同じ要件。
- **[オンクリック] リンク**: ロゴをポイントする URL の場所を追加します。 ロゴは、会社の Web サイトなど、任意の会社リソースへのリンクとして使用できます。 ロゴの URL の場所を選択しない場合は、既定でホーム ページOfficeされます。

**[保存]** を選び、変更内容を保存します。

:::image type="content" source="../../media/Logos_Tab.png" alt-text="スクリーンショット: ロゴ オプションを示す [ロゴ] タブ":::

ロゴは、いつでも削除できます。 [ロゴ] ページに戻 **り、[** 削除] を **選択します**。
  
## <a name="colors-choose-theme-colors"></a>色: テーマの色を選択する

[色 **] ページ** で、既定の色を設定し、使用するロゴを選択できます。

- **ナビゲーション バーの色**: ナビゲーション バーの背景に使用する色を選択します。 ナビゲーション バーは、すべてのページの上部に表示されます。
- **テキストとアイコンの色**: 上部ナビゲーション バーのテキストとアイコンに使用する色を選択します。
- **アクセントの色**: 白または明るい背景によく表示される色を選択します。 アクセントカラーは、白または明るい背景に表示されるいくつかのリンクやボタンの色を付けするために使用されます。 たとえば、アクセントの色は、ユーザーの受信トレイとユーザーの Office.com ポータル ページの要素を色付けするために使用されます。
- **[色のリセット**] : 色を既定の色にリセットするには、このリンクを選択します。

:::image type="content" source="../../media/default-theme-colors1.png" alt-text="スクリーンショット: 組織の既定のテーマの色を示す [色] タブ":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>組織には、すべての従業員のテーマが既に設定されています。 この変更方法

既定のテーマは、引き続きすべての従業員に表示されます。新しいグループ テーマを追加すると、そのテーマに関連付Microsoft 365グループでのみ使用できます。

### <a name="whydont-isee-group-themes-in-the-admin-center"></a>管理センターにグループテーマが表示されるのがどうしてですか?

会社のテーマをカスタマイズできるのは、グローバル管理者のみです。グローバル リーダーには読み取り専用アクセス権があります。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>組織に対して設定できるテーマの数  

最大 5 つのテーマを作成できます。 既定のテーマと 4 つのグループ テーマ。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>グループの代わりにセキュリティ グループまたは配布グループMicrosoft 365できますか?

いいえ、新しいグループ テーマは、セキュリティ グループや配布グループではなく、Microsoft 365グループにマップする必要があります。

> [!NOTE]
> 配布グループは[、配布グループを Microsoft 365グループ](../manage/upgrade-distribution-lists.md)にOutlook。

### <a name="can-imanually-assign-a-theme-independent-ofmicrosoft-365-groups"></a>グループに依存しないテーマを手動で割りMicrosoft 365できますか?  

いいえ、新しいグループ テーマは、1 つ以上のグループにマップMicrosoft 365があります。 グループのメンバーであるユーザー Microsoft 365、そのグループにテーマが適用されます。 管理センター[の [グループ] に移動して](../create-groups/create-groups.md)、Microsoft 365グループに設定 ****   >  **メンバー** を作成して追加できます。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>ユーザーが複数のグループ テーマに割り当てられている場合は、どうなるでしょうか。  

複数のグループ テーマに割り当てられているユーザーには、既定のテーマが表示されます。  

### <a name="why-cant-i-delete-the-default-theme"></a>既定のテーマを削除できない理由  

既定のテーマは、すべてのグループ テーマが削除された後にのみ削除できます。 グループ テーマを削除する前に、すべてのグループ テーマを削除してください。

### <a name="why-am-i-receiving-an-error-message-every-time-i-uploadalogo-url"></a>ロゴ URL をアップロードする度にエラー メッセージが表示される理由。  

使用しているロゴが、パブリックアドレス指定可能な URL として指定されている必要があります。 次の手順に[従って、ロゴ](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet)を Azure Blob Storageまたはオンライン Office 365 Content Delivery Network[にアップロードSharePointします](../../enterprise/use-microsoft-365-cdn-with-spo.md)。

### <a name="why-am-i-receiving-themessagedoesnt-meet-minimum-color-contrast-ratio-of-451"></a>"4.5:1 の最小色コントラスト比を満たしていない" というメッセージが表示される理由

テキスト、アイコン、またはボタンの色と背景色の推奨コントラスト比は 4.5:1 です。 この推奨事項を上書きしてテーマを保存できます。これは要件ではありません。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>テーマを定義する場合、このMicrosoft 365どの場所で使用されますか?

すべてのテーマは、グループ スイート ヘッダーの一部として、組織内のすべてのユーザーのトップ ナビゲーション Microsoft 365表示されます。  
  
## <a name="related-content"></a>関連コンテンツ

[[マイ アプリ] ページとアプリ 起動ツール](../manage/customize-the-app-launcher.md) (記事)\ にカスタム タイルを追加する
[管理者向Microsoft 365グループの概要](../create-groups/office-365-groups.md)(記事)
