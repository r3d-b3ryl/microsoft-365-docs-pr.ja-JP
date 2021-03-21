---
title: Microsoft 365 でテキスト区切りデータをアーカイブするコネクタをセットアップする
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
description: 管理者は、Globanet から Microsoft 365 にテキスト区切りデータをインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 00003cbd897cc80b0596dbb7e5988f010cd7f7e2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925011"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>テキスト区切りデータをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織のユーザー メールボックスにテキスト区切りデータをインポートおよびアーカイブします。 Globanet は[](https://globanet.com/text-delimited)、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたテキスト区切りコネクタを提供します。 コネクタは、テキストで区切られたデータ ソースから電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

テキストで区切られたデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 テキストで区切られたデータ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-the-text-delimited-data"></a>テキスト区切りデータのアーカイブの概要

次の概要では、Microsoft 365 でコネクタを使用してテキストで区切られたソース情報をアーカイブするプロセスについて説明します。

![テキストで区切られたデータのアーカイブ ワークフロー](../media/TextDelimitedConnectorWorkflow.png)

1. 組織は、テキストで区切られたソースを使用して、テキストで区切られたサイトを設定および構成します。

2. 24 時間に 1 回、テキストで区切られたソースからのチャット メッセージが Globanet Merge1 サイトにコピーされます。 コネクタは、コンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成するテキスト区切りコネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。 Text- **Delimited** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー のメールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのメッセージには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 でテキスト区切りコネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-text-delimited-connector"></a>手順 1: テキスト区切りコネクタを設定する

最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、テキストで区切られたデータ用のコネクタを作成することです。 

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) テキスト区切り] に移動  >  **し、[データ コネクタ] をクリックします**。

2. [テキストで **区切られた製品の説明] ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトでテキスト区切りコネクタを構成する

2 番目の手順は、Merge1 サイトでテキスト区切りコネクタを構成することです。 Globanet Merge1 サイトでテキスト区切りコネクタを構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。 テキスト区切りソース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-text-delimited-connector"></a>手順 4: テキスト区切りコネクタを監視する

テキスト区切りコネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、[ **テキスト区切りコネクタ]** を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。