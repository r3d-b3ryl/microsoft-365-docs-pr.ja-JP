---
title: Microsoft 365 で Facebook データから Workplace をアーカイブするコネクタを設定する
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
description: 管理者は、Globanet の Merge1 サイトにアーカイブされている Facebook から Microsoft 365 に Workplace からデータをインポートおよびアーカイブするコネクタを設定できます。 コネクタをセットアップするには、Globanet で作業する必要があります。このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブできます。これにより、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 0bcea998e857365b512b2a6f773dca17a85c08f9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619853"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Facebook データから Workplace をアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Workplace から Microsoft 365 組織のユーザー メールボックスにデータをインポートしてアーカイブします。 Globanet は、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Facebook コネクタから [Workplace](https://globanet.com/workplace/) を提供します。 コネクタは、チャット、添付ファイル、投稿、ビデオなどのコンテンツを Workplace から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Workplace データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Facebook コネクタから Workplace を使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Facebook データからの Workplace のアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Workplace データをアーカイブするプロセスについて説明します。

![Facebook データからの Workplace のアーカイブ ワークフロー](../media/WorkplaceConnectorWorkflow.png)

1. 組織は Facebook から Workplace と一緒に作業し、Workplace サイトをセットアップして構成します。

2. 24 時間ごとに、Workplace のアイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、これらのアイテムの内容を電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成した Facebook コネクタからの Workplace は、毎日 Globanet Merge1 に接続し、Workplace アイテムを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 Facebook から **Workplace** という名前の受信トレイ フォルダー内にサブフォルダーが作成され、Workplace アイテムがフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Workplace アイテムには、このプロパティが含まれているので、すべてのチャットまたは投稿参加者のメール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 このアカウントは、手順 1 でコネクタを作成するときにサインインします。

- コンプライアンスと電子情報開示の目的で API を介して Workplace からデータを取得するカスタム https://my.workplace.com/work/admin/apps/ 統合を作成します。

   統合を作成すると、Workplace プラットフォームは認証に使用されるトークンを生成するために使用される一連の固有の資格情報を生成します。 これらのトークンは、手順 2 の Facebook コネクタ構成ウィザードの Workplace で使用されます。 アプリケーションを作成する方法の詳細な手順については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

- 手順 1 で Facebook コネクタから Workplace を作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>手順 1: Facebook コネクタから Workplace をセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにアクセスし、Workplace データ用のコネクタを作成することです。

1. Facebook から [https://compliance.microsoft.com](https://compliance.microsoft.com/) [Data **connectors** Workplace] に移動  >  **してクリックします**。

2. Facebook 製品の **説明ページの Workplace** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Facebook コネクタから Workplace を構成する

2 番目の手順は、Merge1 サイトで Facebook コネクタから Workplace を構成することです。 Facebook コネクタから Workplace を構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [外部ユーザー **を Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。 Workplace アイテムには、組織内のユーザー *の電子* メール アドレスを含む Email というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>手順 4: Facebook コネクタから Workplace を監視する

Facebook コネクタから Workplace を作成すると、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブを** クリックし **、Facebook** コネクタから Workplace を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
