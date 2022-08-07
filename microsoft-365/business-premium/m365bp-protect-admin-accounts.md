---
title: Microsoft 365 Business Premium で管理者アカウントを保護する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business Premium で管理者アカウントを設定して保護する方法について説明します。
ms.openlocfilehash: 6534cf3285aa08b4b9da4ea65965751a1ac14a6b
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67277029"
---
# <a name="protect-your-administrator-accounts-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium で管理者アカウントを保護する

管理者アカウントには管理者特権が付与されているため、ハッカーやサイバー犯罪者にとっては重要なターゲットになります。この記事では、次の事項について説明します。

- [緊急時に別の管理者アカウントを設定する方法](#create-other-admin-accounts)。
- [緊急管理者アカウントを作成する方法](#create-an-emergency-admin-account)。
- [自分でユーザー アカウントを作成する方法](#create-a-user-account-for-yourself)。
- [管理者アカウントを保護する方法](#protect-admin-accounts)。
- [その他の推奨事項](#additional-recommendations) と [次の目的](#next-objective)。

Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者 (社内管理者とも呼ばれます) になります。 グローバル管理者は、ユーザー アカウントとその他のすべての設定を Microsoft 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で最終的に制御できますが、アクセス度が異なるさまざまな管理者アカウントが多数存在します。 [管理者ロールの](/office365/admin/add-users/about-admin-roles)種類ごとに異なるアクセス レベルについて詳しくは、管理者ロールに関するページをご覧ください。

## <a name="create-other-admin-accounts"></a>別の管理者アカウントを作成する

管理者アカウントは、Microsoft 365 の管理にのみ使用します。 管理者は、Office アプリを定期的に使用するための別のユーザー アカウントを持ち、管理アカウントを、アカウントとデバイスを管理するために必要な場合、または他の管理機能で作業する場合のみに使用する必要があります。 また、管理者アカウントから Microsoft 365 ライセンスを削除して、追加のライセンス料金が発生しないようにすることをお勧めします。

管理者が別の信頼できる従業員に、少なくとも 1 つの別のグローバル管理者アカウントを設定し、管理者アクセス権を付与する必要があります。 ユーザー管理用に別の管理者アカウントを作成することもできます (このロールは **ユーザー管理の管理者** と呼ばれます)。 詳細については、「[管理者の役割について](/office365/admin/add-users/about-admin-roles)」を参照してください。

> [!IMPORTANT]
> 一連の管理者アカウントを設定することをお勧めしますが、組織のグローバル管理者の数を制限する必要があります。 さらに、最小特権アクセスの概念に従うことをお勧めします。つまり、業務を実行するのに必要なデータと操作にのみアクセス権を付与します。 [最小特権の原則について詳しくは、こちらを参照してください](/azure/active-directory/develop/secure-least-privileged-access)。 

追加の管理者アカウントを作成するには:

 1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

    ![左側のナビゲーションで [ユーザー] と [アクティブ なユーザー] の順に選択します。](../media/Activeusers.png)

 2. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択します。 

 3. **[ユーザーの追加]** パネルで、名前やユーザー名の情報などの基本情報を入力します。

 4. **[製品ライセンス]** 情報を入力して設定します。

 5. **[オプションの設定]** で、管理センターへのアクセスを追加するなど、ユーザーのロールを必要に応じて定義します。

    :::image type="content" source="media/m365bp-global-admin.png" alt-text="新しいユーザー ロールを定義します。":::

 6. 設定を完了してから確認し、詳細を確定するために **[追加の完了]** を選択します。

## <a name="create-an-emergency-admin-account"></a>緊急管理者アカウントを作成する

また、多要素認証 (MFA) で設定されていないバックアップ アカウントを作成して、誤って自分をロックアウトしないようにする必要があります (たとえば、2 つ目の認証形式として使用しているスマートフォンを紛失した場合)。 このアカウントのパスワードがフレーズであること、または 16 文字以上であることを確認します。 緊急管理者アカウントは多くの場合、"ブレークグラス アカウント" と呼ばれます。

## <a name="create-a-user-account-for-yourself"></a>自分のユーザー アカウントを作成する

管理者である場合は、メールの確認など、通常の業務タスク用のユーザー アカウントが必要です。 どちらがどちらであるかを把握できるように、アカウントに名前を付けます。 たとえば、管理者の資格情報が  *Alice.Chavez <span></span>@Contoso.org* のようなものだとすると、通常のユーザー アカウントが *Alice <span></span>@Contoso.com* のようにします。

新しいユーザー アカウントを作成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

2. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択して、**[ユーザーの追加]** パネルで名前などの情報を入力します。

3. **[製品ライセンス]** セクションで、**[Microsoft 365 Business Premium (管理アクセスなし)]** のチェック ボックスをオンにします。

4. **[オプションの設定]** セクションにある、**[ユーザー (管理センターへのアクセスなし)]** ラジオ ボタンの選択は既定のままにします。

5. 設定を完了してから確認し、詳細を確定するために **[追加の完了]** を選択します。

## <a name="protect-admin-accounts"></a>管理者アカウントを保護する

すべての管理者アカウントを保護するには、次の推奨事項に従ってください:

- すべての管理者アカウントにパスワードレス認証 (Windows Hello や Authenticator アプリなど) または多要素認証を使用するように要求します。 パスワードレス認証が重要である理由の詳細については、 [｢Microsoft セキュリティのホワイト ペーパー: パスワードレス保護](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2KEup)｣ を参照してください。

- 管理者にカスタムのアクセス許可を使用しないでください。 特定のユーザーにアクセス許可を付与する代わりに、Azure Active Directory (Azure AD) のロールを使用してアクセス許可を割り当てます。 また、手元のタスクを実行するために必要なデータと操作のみにアクセス権を付与します。 [Azure AD の最小特権ロールについて説明します](/azure/active-directory/roles/delegate-by-task)。

- 可能な場合は、組み込みのロールを使用してアクセス許可を割り当てます。 Azure ロールベースのアクセス制御 (RBAC) には、使用できるいくつかの組み込みロールがあります。 [Azure AD の組み込みロールの詳細について説明します](/azure/active-directory/roles/permissions-reference)。

## <a name="additional-recommendations"></a>追加の推奨事項:

- 管理者アカウントを使用する前に、個人用メール アカウントを含め、無関係なすべてのブラウザー セッションとアプリを閉じます。 プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。

- 管理者タスクを完了したら、必ずブラウザー セッションからサインアウトしてください。

## <a name="next-objective"></a>次の目標

[Microsoft 365 Business Premium の脅威に対する保護を強化する](m365bp-increase-protection.md)
