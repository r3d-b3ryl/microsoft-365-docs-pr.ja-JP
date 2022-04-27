---
title: Microsoft 365でテキスト区切りのデータをアーカイブするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理者は、Veritas からMicrosoft 365にテキスト区切りデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 9b61b37a1748208a7bd0c55e7659acc9d9066767
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090497"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>テキスト区切りデータをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、テキスト区切りのデータをインポートし、Microsoft 365組織内のユーザー メールボックスにアーカイブします。 Veritas には、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらの項目をMicrosoft 365にインポートするように構成[されたテキスト区切りコネクタ](https://globanet.com/text-delimited)が用意されています。 コネクタは、テキスト区切りのデータ ソースから電子メール メッセージ形式にコンテンツを変換し、それらのアイテムをMicrosoft 365のユーザーのメールボックスにインポートします。

テキスト区切りのデータがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 テキスト区切りのデータ コネクタを使用して、Microsoft 365でデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-the-text-delimited-data"></a>テキスト区切りデータのアーカイブの概要

次の概要では、コネクタを使用してテキスト区切りのソース情報をMicrosoft 365にアーカイブするプロセスについて説明します。

![テキスト区切りデータのアーカイブ ワークフロー。](../media/TextDelimitedConnectorWorkflow.png)

1. 組織は、テキスト区切りソースと連携して、テキスト区切りサイトを設定および構成します。

2. 24 時間に 1 回、テキスト区切りのソースからのチャット メッセージが Veritas Merge1 サイトにコピーされます。 また、コネクタはコンテンツを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成するテキスト区切りコネクタは、毎日 Veritas Merge1 サイトに接続され、Microsoft クラウド内の安全なAzure Storage場所にメッセージを転送します。

4. コネクタは、手順 3. の説明に従って、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。 **テキスト区切り** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべてのメッセージにはこのプロパティが含まれています。このプロパティには、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>開始する前に

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 でテキスト区切りコネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-text-delimited-connector"></a>手順 1: テキスト区切りコネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、テキストで区切られたデータのコネクタを作成します。

1. **Data** **connectorsText-Delimited** >  に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **テキスト区切りの** 製品説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトでテキスト区切りコネクタを構成する

2 番目の手順では、Merge1 サイトでテキスト区切りコネクタを構成します。 Veritas Merge1 サイトでテキスト区切りコネクタを構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [**外部ユーザーを Microsoft 365 ユーザーにマップ** する] ページで、自動ユーザー マッピングを有効にします。 テキスト区切りソース項目には、組織内のユーザーの電子メール アドレスを含む *Email* という名前のプロパティが含まれます。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-text-delimited-connector"></a>手順 4: テキスト区切りのコネクタを監視する

テキスト区切りコネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **テキスト区切り]** コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。