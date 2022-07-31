---
title: パスワードをリセットする
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: medium
ms.date: 07/19/2022
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
description: Microsoft 365 Business Premiumのユーザーのパスワードをリセットします。
ms.openlocfilehash: 66cfb73693a11c2229c294aa09fd90b54c14c413
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66995372"
---
# <a name="reset-passwords-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premiumでパスワードをリセットする

必要に応じて、自分とユーザーのパスワードをリセットする方法について説明します。 管理者は、ユーザーのパスワードを忘れた場合にリセットできます。

## <a name="user-initiated-password-reset"></a>ユーザーが開始したパスワードのリセット

ユーザーが新しいパスワードを要求すると、パスワード リセット要求が電子メールで送信されます。

1. パスワードをリセットするには、アプリ起動ツールを開き **、管理** を選択し、資格情報でログインします。

2. Microsoft 365 管理センターで[**ユーザー]**、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**アクティブなユーザー**</a>] の順に選択し、リセットを要求したユーザーの横にあるキー アイコンを選択します。

3. ランダムなパスワードを自動的に作成するには、[**自動生成のパスワード**] を選択します。

4. **[リセット]** を選択します。

## <a name="admin-initiated-password-reset"></a>管理によって開始されたパスワード リセット

管理者がアカウントに対してパスワードリセットを強制する必要がある場合があります。

1. 管理 センターで、[**ユーザー**<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブ ユーザー</a>\>] ページに移動します。

2. [ **アクティブなユーザー** ] ページで、リセットする特定のユーザーを選択し、[ **パスワードのリセット**] を選択します。

3. [**パスワードのリセット**] ページに表示される手順を実行して、ユーザーの新しいパスワードを自動生成するかユーザー用に新しいパスワードを作成し、[**リセット**] を選択します。  

4. ユーザーが受信可能なメール アドレスを入力して、ユーザーが新しいパスワードを受信できるようにします。ユーザーに連絡を取り、ユーザーがパスワードを受け取ったことを確認します。

## <a name="let-users-reset-their-own-passwords"></a>ユーザーが自分でパスワードをリセットできるようにする

セルフサービスのパスワード リセットを設定することを強くお勧めします。 この方法では、ユーザーのパスワードを手動でリセットする必要はありません。 詳細については、「[Office 365 でユーザーが自分のパスワードを再設定する](/admin/add-users/let-users-reset-passwords.md)」を参照してください。

## <a name="reset-my-admin-password"></a>管理者パスワードをリセットする

パスワードを忘れたが Microsoft 365 にサインインできる場合は、次の手順を使用します。たとえば、パスワードはブラウザーに保存されるためです。

1. **マイ アカウント** > **の個人情報**>右上隅にある自分の名前 (アイコン) を選択します。

2. [ **連絡先の詳細**] で、 **代替メール** が正確であり、携帯電話番号が入力されていることを再確認します。 正しくない場合は、この場で変更します。

3. サインアウト: 右上隅 \>のサイン **アウト** で自分の名前を選択します。

4. もう一度サインインします: ユーザー名を入力し \> [**次へ**] \> [**パスワードを忘れた場合**] の順に選択します。

5. ウィザードの手順に従って、パスワードをリセットします。 ウィザードでは、あなたがパスワードをリセットするための適切なユーザーであることが、代替連絡先情報を使用して確認されます。

パスワードを忘れ、サインインできない場合:

- 社内の別のグローバル管理者にパスワードのリセットを依頼します。

- 携帯電話番号を含む別の連絡先情報が提供されていることを確認します。

## <a name="reset-all-business-passwords-for-everyone-at-the-same-time"></a>すべてのユーザーのすべてのビジネス パスワードを同時にリセットする

<a name="bkmk_forgot"> </a>

次の手順は、数十のユーザーを抱える会社を対象にしています。 ユーザー数が数百または数千人の場合は、パスワードを一括でリセットする方法 (一度に最大 40 ユーザー) に関する次のセクションを参照してください。
  
1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。

2. [**表示名**] の横にある、社内のすべてのユーザーを選択するオプションを選択します。 次に、自分の選択を解除します。 自分以外のユーザーのパスワードをリセットするのと同時に、自分のパスワードをリセットすることはできません。

3. [**パスワードのリセット**] を選択します。

4. [**パスワードのリセット**] ページの指示に従って操作し、[**リセット**] を選択します。  パスワードの自動生成を選択した場合、新しい一時パスワードが表示されます。

5. 一時パスワードを受信できるメール アドレスを入力します。 ユーザーの一時パスワードをユーザーに通知する必要があります。
  
## <a name="reset-business-passwords-in-bulk"></a>ビジネス パスワードを一括でリセットする

<a name="bkmk_forgot"> </a>

複数のアカウントのパスワードをリセットするには、PowerShell を使用します。 Eyal Doron による次の投稿を確認してください: [PowerShell でパスワードを管理する](https://go.microsoft.com/fwlink/?linkid=853696)

概要については、「 [PowerShell を使用した Microsoft 365 の管理](../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)」を参照してください。
  
## <a name="related-content"></a>関連コンテンツ
  
[ユーザーが自分のパスワード](../admin/add-users/let-users-reset-passwords.md)
をリセットできるようにする[Microsoft 365 for business](../admin/add-users/reset-passwords.md)
 のパスワードをリセットする[個々のユーザーのパスワードを無期限](../admin/add-users/set-password-to-never-expire.md) 
に設定する[組織のパスワード有効期限ポリシーを設定する](../admin/manage/set-password-expiration-policy.md)