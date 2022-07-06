---
title: インサイダー リスク管理通知のテンプレート
description: Microsoft Purview のインサイダー リスク管理通知テンプレートについて説明します
keywords: Microsoft 365、Microsoft Purview、インサイダー リスク、リスク管理、コンプライアンス
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 7af1152d1393aaaf9eeb242c78b280cf0e9d80e6
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639800"
---
# <a name="insider-risk-management-notice-templates"></a>インサイダー リスク管理通知のテンプレート

Insider リスク管理通知テンプレートを使用すると、ポリシー一致と確認済みアラートを生成したアクティビティに対してケースが作成されたときに、ユーザーに電子メール メッセージを自動的に送信できます。 ケースを生成するほとんどのアラートでは、ユーザー アクションは誤った意図のない誤ったアクティビティや不注意なアクティビティの結果です。 通知は、ユーザーに対して、より注意を払うための簡単なリマインダーとして機能します。また、情報へのリンクを提供してリフレッシュトレーニングを行ったり、企業のポリシー リソースにリンクしたりできます。 通知は、内部コンプライアンス トレーニング プログラムの重要な部分であり、定期的なリスク アクティビティを持つユーザーの文書化された監査証跡を作成するのに役立ちます。

ケース解決プロセスの一環として、ポリシー一致の電子メール リマインダー通知をユーザーに送信する場合は、通知テンプレートを作成します。 通知は、確認中の特定のケースに関連付けられているユーザーの電子メール アドレスにのみ送信できます。 ポリシー一致に適用する通知テンプレートを選択するときは、テンプレートで定義されているフィールド値を受け入れるか、必要に応じてフィールドを上書きするかを選択できます。

## <a name="notice-templates-dashboard"></a>[通知テンプレート] ダッシュボード

**通知テンプレートダッシュボード** には、構成された通知テンプレートのリストが表示され、新しい通知テンプレートを作成できます。 通知テンプレートは、最新の通知テンプレートを最初に、日付の逆順でリストに表示されます。

![Insider リスク管理通知テンプレート ダッシュボード。](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>通知用の HTML

通知用の単純なテキストベースの電子メール メッセージを作成する場合は、通知テンプレートのメッセージ本文フィールドで HTML を使用して、より詳細なメッセージを作成できます。 次の例では、基本的な HTML ベースの電子メール通知テンプレートのメッセージ本文の形式を示します。

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> インサイダー リスク管理通知テンプレートの HTML href 属性の実装では、現在、URL 参照の二重引用符ではなく単一引用符のみがサポートされています。

## <a name="create-a-new-notice-template"></a>新しい通知テンプレートを作成する

新しいインサイダー リスク管理通知テンプレートを作成するには、Microsoft Purview コンプライアンス ポータルの **Insider リスク管理** ソリューションで通知作成ツールを使用します。

次の手順を実行して、新しいインサイダー リスク管理通知テンプレートを作成します。

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com)で、**Insider リスク管理** に移動し、[**通知テンプレート**] タブを選択します。
2. [ **通知テンプレートの作成** ] を選択して、通知作成ツールを開きます。
3. [ **新しい通知テンプレートの作成** ] ページで、次のフィールドに入力します。
    - **テンプレート名**: 通知のフレンドリ名を入力します。 この名前は、通知ダッシュボードの通知の一覧と、ケースから通知を送信するときに通知の選択リストに表示されます。
    - **送信元**: 通知の送信者の電子メール アドレスを入力します。 このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信されたすべての通知の [ **差** 出人] フィールドに表示されます。
    - **Cc フィールドと Bcc** フィールド: サブスクリプションの Active Directory から選択された、ポリシー一致の通知を受け取るオプションのユーザーまたはグループ。
    - **件名**: メッセージの件名行に表示される情報は、テキスト文字をサポートします。
    - **メッセージ本文: メッセージ本文** に表示される情報は、テキストまたは HTML 値をサポートします。
4. **[作成]** を選択して通知テンプレートを作成して保存するか、[**キャンセル]** を選択して通知テンプレートを保存せずに閉じます。

## <a name="update-a-notice-template"></a>通知テンプレートを更新する

既存のインサイダー リスク管理通知テンプレートを更新するには、次の手順を実行します。

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com)で、**Insider リスク管理** に移動し、[**通知テンプレート**] タブを選択します。
2. 通知ダッシュボードで、管理する通知テンプレートを選択します。
3. 通知の詳細ページで、[編集] を選択 **します**。
4. **[編集]** ページでは、次のフィールドを編集できます。
    - **テンプレート名**: 通知の新しいフレンドリ名を入力します。 この名前は、通知ダッシュボードの通知の一覧と、ケースから通知を送信するときに通知の選択リストに表示されます。
    - **送信元**: 通知の送信者の電子メール アドレスを更新します。 このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信されたすべての通知の [ **差** 出人] フィールドに表示されます。
    - **Cc フィールドと Bcc** フィールド: サブスクリプションの Active Directory から選択されたポリシー一致の通知を受け取るオプションのユーザーまたはグループを更新します。
    - **件名**: メッセージの件名行に表示される更新情報は、テキスト文字をサポートします。
    - **メッセージ本文: メッセージ本文** に表示される情報を更新し、テキストまたは HTML 値をサポートします。
5. **[保存] を** 選択して通知を更新して保存するか、[**キャンセル]** を選択して通知テンプレートを保存せずに閉じます。

## <a name="delete-a-notice-template"></a>通知テンプレートを削除する

既存のインサイダー リスク管理通知テンプレートを削除するには、次の手順を実行します。

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com)で、**Insider リスク管理** に移動し、[**通知テンプレート**] タブを選択します。
2. 通知ダッシュボードで、削除する通知テンプレートを選択します。
3. ツール バーの **[削除** ] アイコンを選択します。
4. 通知テンプレートを削除するには、削除ダイアログで **[はい** ] を選択します。 削除を取り消すには、[キャンセル] を選択 **します**。
