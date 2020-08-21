---
title: ATP の安全なリンク機能を使用して「書き換けないカスタム URL リストを設定する」
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 ATP の安全なリンク ポリシーのユーザー グループに対して、ユーザーのブロック URL のカスタムのリストと書き換Officeのない URL のリストを設定する方法について説明します。
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825235"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>ATP の安全なリンク機能を使用して「書き換けないカスタム URL リストを設定する」

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 ホーム ユーザーで Outlook の安全なリンクに関する情報をお見しいとする場合は、「詳細設定またはセキュリティ [Outlook.comを参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP)[custom blocked URLs](set-up-a-custom-blocked-urls-list-atp.md)により、組織はユーザーがメール メッセージや特定の Office ドキュメントの Web アドレス (URL) をクリックした場合にそれらの URL に移動することが禁止されるので、カスタムのブロック URL を設定できます。 また、組織では、組織内の特定のグループに対して、カスタムの「書き換えない」リストを指定することもできます。 「書き換えない」リストを使用すると、一部のユーザーは、他のユーザーがアクセス許可リストの ATP の安全なリンクによって [ブロックされている URL Officeを使用できます](atp-safe-links.md)。

この記事では、ATP の安全なリンクのスキャンから除外される URL のリストを指定する方法と、注意する必要があります。

> [!NOTE]
> 組織で安全なリンク ポリシーを使用している場合、サード パーティのフィッシング テストでサポートされている方法は"書き換えない" リストのみです。

## <a name="set-up-a-do-not-rewrite-list"></a>「書き換えない」の一覧を設定する

ATP の安全なリンク保護では、組織の禁止 URL リストや例外の「書き換えない」一覧など、いくつかのリストを使用します。 必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストをセットアップできます。 これは、組織内の特定の受信者に適用する安全なリンク ポリシーを追加または編集する場合に行います。

ATP ポリシーを編集 (または定義) するには、適切な役割が割り当てられている必要があります。 次の表にいくつかの例を示します。 詳細については、コンプライアンス センター [の「アクセス許可」&を参照してください](permissions-in-the-security-and-compliance-center.md)。

|役割|参照先/割り当て方法|
|---|---|
|全体管理者|Microsoft 365 を購入するためにサインアップするユーザーは、既定ではグローバル管理者です。 (詳細については [、Microsoft 365 の管理者ロール](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) の詳細を参照してください)。|
|セキュリティ管理者|Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理|Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)|
|

> [!TIP]
> 役割とアクセス許可の詳細については、「アクセス許可 [」コンプライアンス センターの&、「アクセス許可」を参照してください](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>カスタム "書き換えない" URL リストを表示または編集するには

1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。

2. 左側のナビゲーションでは、[脅威**管理ポリシーの** \> **安全なリンク** \> **] の下に**

3. 特定の **受信者に適用するポリシー セクション** で、[ **新規** 作成] を選択し (新しいボタンはプラス記号 ( **+** )) を選びます。 既存のポリシーを編集することもできます。<br/>![Choose New to add a Safe Links policy for specific email recipients](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. ポリシーの名前と説明を指定します。

5. URL **は** 書き換えられ、ユーザーがリンクをクリックすると既知の悪意のあるリンクの一覧と照合されます。

6. [次の **URL を書き換えてはいけない** ] セクションで、[ **有効な URL を入力してください] ボックスを** オンにし、URL を入力して、プラス記号 (+) を選択します。

7. [ **適用先]** セクションで **、[受信者がメンバーである**もの] を選択し、ポリシーに含めるグループを選択します。 **[Add]**(追加) を選び **、[OK] を選択します**。

8. 画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。

> [!NOTE]
> ブロック URL の組織のカスタム リストを確認します。 [「ATP の安全なリンク」を使用して、カスタムのブロック URL リストを設定する方法を確認する](set-up-a-custom-blocked-urls-list-atp.md)。

## <a name="important-points-to-keep-in-mind"></a>注意事項

- 「書き換えない」一覧に指定した URL は、指定した受信者に対する ATP の安全なリンク スキャンから除外されます。

- 一般的に使用される内部 URL を "書き換えない" リストに追加して、ユーザー エクスペリエンスを向上させることを検討してください。 たとえば、Skype for Business、Sharepoint などのオンプレミス サービスがある場合は、それらの URL をリストに追加してスキャンから除外することができます。

- URL の一覧が既に "書き換えない" 一覧の場合は、該当する一覧を確認してワイルドカードを追加します。 たとえば、既存のリストにエントリが含まれており、ポリシーに含めるような `https://contoso.com/a` `https://contoso.com/a/b` サブパスを含める場合は、エントリにワイルドカードを追加して、同様の外観を持つようにします `https://contoso.com/a/*` 。

- ATP の安全なリンク ポリシーに「書き換えない」リストを指定した場合、最大 3 \* つのワイルドカード ( ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、指定したドメインのサブドメインおよびパスにアクセスできるため、エントリは同 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` じには設定されません。

次の表に、入力できる項目と、それらのエントリの効果の例を示します。

****

|エントリの例|機能|
|---|---|
|`contoso.com`|受信者が、サブドメインやパスのような `https://contoso.com` サイトにアクセスできますが、サブドメインやパスはアクセスできません。|
|`*.contoso.com/*`|受信者が、ドメイン、サブドメイン、パス (,、.. など) `https://www.contoso.com` にアクセス `https://www.contoso.com` `https://maps.contoso.com` できます `https://www.contoso.com/a` 。 <br/><br/> このエントリは、不用のある可能性のあるサイトが含まれていないため、このエントリの値はかなり `*contoso.com*` 大きく優れ `https://www.falsecontoso.com` ており、 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|特定の受信者がたとえばのようなサイトにアクセス `https://contoso.com/a` できますが、次のようなサブパスはアクセスできません。 `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|特定の受信者がいいね!や、次のような `https://contoso.com/a` サイトにアクセスできます。 `https://contoso.com/a/b`|
|
