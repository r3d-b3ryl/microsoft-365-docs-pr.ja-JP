---
title: Webex にコネクタをセットアップし、TeamsデータをMicrosoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Veritas の Webex からデータをインポートおよびアーカイブするコネクタをセットアップし、TeamsのコネクタMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 7041fcb5b9c284969047f9db9719560be49a7993952da44128ba5bfbdd8d5aca
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53820620"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Webex データをアーカイブするコネクタをTeamsする

Webex サーバーからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの Veritas コネクタを使用Teams組織内のユーザー メールボックスMicrosoft 365します。 Veritas には[、Webex](https://globanet.com/webex-teams/) Teams通信アイテムをキャプチャしてインポートするように構成された Webex TeamsコネクタがMicrosoft 365。 コネクタは、組織の Webex Teams アカウントからの 1:1 チャット、グループ会話、チャネル会話、添付ファイルなどのコンテンツを Webex Teams から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Webex Teamsデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Webex Teamsコネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-webex-teams-data"></a>Webex データのアーカイブTeams概要

次の概要では、コネクタを使用して Webex データをアーカイブするプロセスTeams説明Microsoft 365。

![Webex データのアーカイブ ワークフロー Teamsする](../media/WebexTeamsConnectorWorkflow.png)

1. 組織は Webex Teamsを使用して Webex サイトをTeamsします。

2. 24 時間に 1 回、Webex Teamsが Veritas Merge1 サイトにコピーされます。 また、コネクタは Webex ファイルTeamsメール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Webex Teams コネクタは、毎日 Veritas Merge1 に接続し、Webex Teams アイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 ユーザー のメールボックスに **Webex Teams** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Webex Teamsには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- Webex アカウントからデータ [https://developer.webex.com/](https://developer.webex.com) をフェッチするアプリケーションをTeamsします。 アプリケーションの作成の手順については、「Merge1 サード パーティ コネクタ ユーザー [ガイド」を参照してください。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   このアプリケーションを作成すると、Webex プラットフォームは一意の資格情報のセットを生成します。 これらの資格情報は、グローバル Merge1 サイトで Webex Teamsコネクタを構成するときに、手順 2 で使用されます。

- 手順 1 で Webex Teams コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-the-webex-teams-connector"></a>手順 1: Webex コネクタをTeamsする

最初の手順は、データ コネクタにアクセスし[、Webex](https://globanet.com/webex-teams/)コネクタをセットアップTeamsです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) Webex]**に** 移動して  >  **、[Webex Teams] をクリックします**。

2. **[Webex Teams** 説明] ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで webex Teamsコネクタを構成する

2 番目の手順は、Merge1 サイトTeams Webex コネクタを構成することです。 Webex コネクタを構成するTeamsについては[、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. **[Webex ユーザーにユーザーをTeamsするMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。 Webex Teamsには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-webex-teams-connector"></a>手順 4: Webex コネクタTeamsする

Webex Teamsコネクタを作成した後、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し **、Webex** Teamsを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。