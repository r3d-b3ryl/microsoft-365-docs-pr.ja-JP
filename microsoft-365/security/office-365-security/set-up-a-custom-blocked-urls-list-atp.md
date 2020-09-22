---
title: ATP の安全なリンクを使用して、ブロックされたカスタムの Url リストを設定する
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Advanced Threat Protection を使用して、組織でブロックされている Url の一覧を設定する方法について説明します。
ms.openlocfilehash: e153d5631c12d52564643477216b777cdbc49433
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201005"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>ATP の安全なリンクを使用して、ブロックされたカスタムの Url リストを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織はブロックされている Web サイト アドレスのユーザー設定リストを所有することができます。URL がブロックされると、ブロックされた URL へのリンクをクリックしたユーザーは次の画像のような[警告ページ](atp-safe-links-warning-pages.md)に移動します。

![このサイトはブロックされています](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

禁止された Url の一覧は、組織の Microsoft 365 for business security teams によって定義されており、そのリストは、Office 365 ATP Safe Links ポリシーでカバーされている組織内のすべてのユーザーに適用されます。

この記事では、[Office 365 の ATP の安全なリンク](atp-safe-links.md)に、組織のユーザー設定のブロック URL リストを設定する方法について説明します。

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>ユーザー設定のブロック URL リストを表示または編集する

[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のユーザー設定のブロック URL リストなど、いくつかのリストを使用します。必要なアクセス許可があれば、組織のユーザー設定リストを設定できます。これを行うには、組織の既定の安全なリンクのポリシーを編集します。

ATP ポリシーを編集 (または定義) するには、次の表に示す役割の 1 つが割り当てられている必要があります。

****

|役割|参照先/割り当て方法|
|---|---|
|グローバル管理者|Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。 (詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) てを参照してください)。|
|セキュリティ管理者|Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理|Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)|
|

> [!TIP]
> 役割とアクセス許可の詳細については、「 [セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>ユーザー設定のブロック URL リストを表示または編集するには

1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。

2. 左側のナビゲーションの **[脅威の管理]** で **[ポリシー]** \> **[安全なリンク]** の順に選びます。

3. **[組織全体に適用されるポリシー]** セクションで、**[既定]**、**[編集]** (編集ボタンは鉛筆に似ています) の順に選びます。<br/>![[編集] をクリックして安全なリンクの保護に関する既定のポリシーを編集する](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>これにより、ブロック URL リストを表示することができます。最初は、URL のリストが表示されないかもしれません。<br/>![既定の安全なリンク ポリシーに適用されるブロック URL リスト](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)

4. **[有効な URL を入力します]** ボックスを選んで、「URL」と入力し、プラス記号 (**+**) を選びます。

5. 画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。

## <a name="a-few-things-to-keep-in-mind"></a>注意事項

URL をリストに追加するときは、次の点に注意してください。

- URL の最後にスラッシュ (**/**) を含めないでください。たとえば、「`https://www.contoso.com/`」と入力する代わりに、「`https://www.contoso.com`」と入力します。

- ドメイン専用の URL (`contoso.com` または `tailspintoys.com` など) を指定することができます。これにより、ドメインを含む URL のクリックがブロックされます。

- 完全なドメイン (`contoso.com` など) はブロックせずにサブドメイン (`toys.contoso.com*` など) を指定することができます。これにより、サブドメインを含む URL のクリックはブロックされますが、完全ドメインを含む URL のクリックはブロックされません。

- URL ごとにワイルドカードのアスタリスク (\*) を 3 つまで含めることができます。次の表は、入力できる内容と、エントリにどのような効果があるかについていくつかの例を示しています。

****

|エントリの例|機能|
|---|---|
|`contoso.com` または `*contoso.com*`|ドメイン、サブドメイン、パス (`https://www.contoso.com`、`https://sub.contoso.com`、`https://contoso.com/abc` など) をブロックします|
|`https://contoso.com/a`|サイト `https://contoso.com/a` をブロックしますが、`https://contoso.com/a/b` のような追加のサブパスはブロックしません|
|`https://contoso.com/a*`|サイト `https://contoso.com/a`、`https://contoso.com/a/b` のような追加のサブパスをブロックします|
|`https://toys.contoso.com*`|サブドメイン (この場合は「toys」) をブロックしますが、他のドメイン URL (`https://contoso.com` や `https://home.contoso.com` など) のクリックを許可します。|
|

> [!NOTE]
> 既定では、Office 365 ATP Safe Links の既定のポリシーでは、ブロックされる URL の一覧には、500の Url のみを追加できます。 個々の URL は128文字を超えることはできません。 ブロックする URL リスト全体は、1万文字を超えることはできません。

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>組織の特定のユーザーに対して例外を定義する方法

他のユーザーに対してブロックされる可能性のある URL を特定のグループが表示できるようにする場合、特定の受信者に適用される ATP の安全なリンクに関するポリシーを指定できます。「[ATP の安全なリンクを使用して、ユーザー設定の "書き換えない" URL リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください。
