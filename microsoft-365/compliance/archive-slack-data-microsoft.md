---
title: Microsoft が提供するデータ コネクタを使用して Slack 電子情報開示データをMicrosoft 365にアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Microsoft が提供する Slack 電子情報開示データ コネクタを設定して使用して、インスタント メッセージング データをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: 418cbbd67444992f366ad5366258e0ea8eccc503
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64992328"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>Slack 電子情報開示データをアーカイブするコネクタを設定する (プレビュー)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft が提供する Slack 電子情報開示データ コネクタは、組織の Slack ワークスペースからMicrosoft 365にインスタント メッセージング データ (メッセージ、添付ファイル、リンク、リビジョンなど) をインポートおよびアーカイブするのに役立ちます。 データ コネクタは Slack API からデータをプルし、それを電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザー メールボックスにインポートします。 Slack データがインポートされたら、訴訟ホールド、Microsoft Purview 電子情報開示 (プレミアム)、通信コンプライアンス、保持設定などのコンプライアンス ソリューションを Slack コンテンツに適用できます。 Slack 電子情報開示データ コネクタを使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Slack 電子情報開示データのアーカイブの概要

次の概要では、Microsoft データ コネクタを使用してMicrosoft 365で Slack データをアーカイブするプロセスについて説明します。

![Slack 電子情報開示のアーカイブ ワークフロー。](../media/SlackMSFTConnectorWorkflow.png)

1. 組織は Slack と連携して Slack ワークスペースを設定および構成します。

2. データ コネクタを設定すると、組織の Slack ワークスペースからのメッセージがMicrosoft 365のユーザー メールボックスにコピーされます。 また、データ コネクタは、チャット メッセージの内容を電子メール メッセージ形式に変換します。

3. コネクタは、変換されたチャット メッセージを特定のユーザーのメールボックスにインポートします。 **Slack 電子情報開示** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、チャット メッセージ アイテムがそのフォルダーにインポートされます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- 組織には、Slack の Enterprise Grid サブスクリプションが必要です。 詳細については、「 [Slack サブスクリプションと機能](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-)」を参照してください。

- データ コネクタを作成するユーザーには、Slack 組織で **組織の所有者** アプリケーション ロールを割り当てる必要があります。 詳細については、「 [Slack のロールの種類](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack)」を参照してください。

- 組織の Slack エンタープライズ アカウントのユーザー名とパスワードを取得します。 これらの資格情報を使用して、データ コネクタを作成するときにこのアカウントにサインインします。 また、シングル サインオン (SSO) を使用するように構成された Slack 組織内の自動ユーザー プロビジョニングを行うことをお勧めします。 [セキュリティ & コンプライアンス センターのロール](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)

- Slack 電子情報開示コネクタを作成するユーザーには、データ コネクタ管理者ロールが割り当てられている必要があります。 このロールは、Microsoft Purview コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

## <a name="step-1-create-a-slack-ediscovery-connector"></a>手順 1: Slack 電子情報開示コネクタを作成する

1. 左側のナビゲーション ウィンドウで <https://compliance.microsoft.com> [ **データ コネクタ** ] に移動してクリックします。

2. [ **概要** ] タブで[ **フィルター** ] をクリックし、[ **Microsoft による**] を選択して、フィルターを適用します。

3. **[Slack 電子情報開示 (プレビュー)]** をクリックします。

4. **Slack 電子情報開示 (プレビュー)** 製品の説明ページで、[**コネクタの追加**] をクリックします。

5. **[サービス利用規約**] ウィザード ページで、[**同意** する] をクリックします。

6. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。 入力した名前は、作成後に [ **データ コネクタ** ] ページでコネクタを識別します。

## <a name="step-2-sign-into-your-slack-organization"></a>手順 2: Slack 組織にサインインする

1. **[Slack へのサインイン**] ウィザード ページで、[**Slack にサインイン**] をクリックして、組織の Slack ワークスペースにサインインします。

2. Slack **の [ワークスペースへのサインイン** ] ページで、データをアーカイブするワークスペースの名前を入力し、[ **続行**] をクリックします。

   Slack ワークスペースの名前とサインインを求めるプロンプトが表示されたページが表示されます。

3. **組織の所有者がここでサインインできる** 文字列のリンクをクリックします。

4. ワークスペースサインイン ページで、組織の Slack エンタープライズ アカウントのメール アドレスとパスワードを入力し、[ **サインイン**] をクリックします。

   正常にサインインすると、コネクタ アプリによって Slack 組織にアクセスするためのアクセス許可を要求するページが表示されます。

5. [ **許可]** をクリックして、アプリが組織を管理できるようにします。

   **[許可**] をクリックすると、Slack ページが閉じ、コネクタ ウィザードの **[ユーザーに対する Slack 電子情報開示ユーザーのマップ**] ページMicrosoft 365表示されます。

## <a name="step-3-specify-the-users-to-import-data-for"></a>手順 3: データをインポートするユーザーを指定する

次のいずれかのオプションを選択して、Slack 電子情報開示データをインポートするユーザーを指定します。

- **組織内のすべてのユーザー**。 すべてのユーザーのデータをインポートするには、このオプションを選択します。

- **訴訟ホールドのユーザーのみ**。 メールボックスが訴訟ホールドに置かれているユーザーに対してのみデータをインポートするには、このオプションを選択します。 このオプションは、LitigationHoldEnabled プロパティが True に設定されているユーザー メールボックスにデータをインポートします。 詳細については、「 [訴訟ホールドの作成](create-a-litigation-hold.md)」を参照してください。

## <a name="step-4-map-users-and-select-data-types-to-import"></a>手順 4: ユーザーをマップし、インポートするデータ型を選択する

1. Slack ユーザーを自分のMicrosoft 365メールボックスにマップするには、次のオプションのいずれかまたは両方を構成します。

   - **自動ユーザー マッピング**。 Slack ユーザー名をメールボックスに自動的にマップMicrosoft 365するには、このオプションを選択します。 コネクタは、すべての Slack メッセージまたはアイテムに含まれる *Email* プロパティの値を使用して行います。 このプロパティには、メッセージのすべての参加者の電子メール アドレスが設定されます。 コネクタが対応するMicrosoft 365 ユーザーに電子メール アドレスを関連付けることができる場合、アイテムはそれらのユーザーのMicrosoft 365 メールボックスにインポートされます。 このオプションを使用するには、Slack 組織に対して SSO が構成されている必要があります。

   - **カスタム ユーザー マッピング**。 また、自動ユーザー マッピングの代わりに (またはそれに加えて) カスタム ユーザー マッピングを使用することもできます。 このオプションを使用すると、ユーザーの Slack メンバー ID を自分のMicrosoft 365メール アドレスにマップする CSV ファイルを作成してアップロードする必要があります。 これを行うには、[**CSV マッピング テンプレートのダウンロード**] をクリックし、組織内のすべてのユーザーの Slack メンバー ID とMicrosoft 365メール アドレスを CSV ファイルに設定し、CSV ファイルを選択してウィザードにアップロードします。 CSV ファイル内の列見出しは変更しないでください。 CSV マッピング ファイルの例を次に示します。

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > ユーザーのメンバー ID は、... をクリックして取得できます。ユーザーのプロファイルのその他のボタンをクリックし、[ **メンバー ID のコピー**] を選択します。 または、Slack [users.list API メソッド](https://api.slack.com/methods/users.list) を使用して、Slack チームのすべてのメンバーの ID を取得することもできます。

   自動ユーザー マッピングを有効にし、カスタム マッピング ファイルを指定した場合、コネクタは最初にカスタム マッピング ファイルを見て、Slack ユーザーをMicrosoft 365メールボックスにマップします。 コネクタで Slack ユーザーに対応する有効なMicrosoft 365 ユーザーが見つからない場合、コネクタは Slack アイテムの *Email* プロパティを使用します。 コネクタで、カスタム マッピング ファイルまたはメッセージ アイテムの *Email* プロパティで有効なMicrosoft 365 ユーザーが見つからない場合、アイテムはインポートされません。

2. [ **インポートするデータ型の選択** ] ウィザード ページで、インポートする Slack データ型を選択します。 すべてのチャネルからメッセージをインポートする場合は、すべてのオプションを選択します。 それ以外の場合は、インポートするデータ型のみを選択します。

     Slack メッセージに加えて、Microsoft 365にインポートする他の種類の Slack コンテンツを指定することもできます。 

3. インポートするデータ型を構成したら、[ **次へ**] をクリックしてコネクタの設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

## <a name="step-5-monitor-the-slack-ediscovery-connector"></a>手順 5: Slack 電子情報開示コネクタを監視する

Slack 電子情報開示コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **Slack 電子情報開示** コネクタを選択してポップアップ ページを表示します。このページには、コネクタに関するプロパティと情報が表示されます。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
