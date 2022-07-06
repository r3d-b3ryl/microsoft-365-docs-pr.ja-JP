---
title: Microsoft 365 で EML データをアーカイブするコネクタを設定する
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
description: 管理者は、Veritas から Microsoft 365 に EML データをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 2d0d0afec6bfb35700ee8b22727f8732f111286a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636669"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a>EML データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Microsoft 365 組織内のユーザー メールボックスに EML データをインポートしてアーカイブします。 EML は、ファイルに保存された電子メール メッセージのファイル拡張子です。 コネクタは、アイテムのコンテンツをソース形式から電子メール メッセージ形式に変換し、アイテムをユーザー メールボックスにインポートします。

EML メッセージがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 EML コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-eml-data"></a>EML データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で EML データをアーカイブするプロセスについて説明します。

![EML データのアーカイブ ワークフロー。](../media/EMLConnectorWorkflow.png)

1. 組織は EML ソースと連携して、EML サイトを設定および構成します。

2. 24 時間に 1 回、EML ソースのコンテンツアイテムが Veritas Merge1 サイトにコピーされます。 このプロセス中、EML ファイルの内容は電子メール メッセージ形式に変換されます。

3. コンプライアンス ポータルで作成する EML コネクタは、毎日 Veritas Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup) で説明した自動ユーザー マッピング プロセスの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。 このプロセス中に、 **EML** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、EML アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべてのメッセージには、このプロパティが含まれています。このプロパティには、コンテンツ アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 で EML コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-an-eml-connector"></a>手順 1: EML コネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、EML データ用のコネクタを作成します。

1. [データ コネクタ EML] に [https://compliance.microsoft.com](https://compliance.microsoft.com/) 移動し、[ **データ コネクタ** > **] を** クリックします。

2. **EML** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-eml-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで EML コネクタを構成する

2 番目の手順は、Veritas Merge1 サイトで EML コネクタを構成することです。 EML コネクタの構成の詳細については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、自動ユーザー マッピングを有効にします。 EML ソースアイテム *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合、EML アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-eml-connector"></a>手順 4: EML コネクタを監視する

EML コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **EML** コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。