---
title: Microsoft 365 で XSLT/XML データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365 の Globanet から XSLT/XML データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: cd41684b84b7899e80ccf8976a9b4c1f6c7e2984
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619843"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>XSLT/XML データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Web ページ ソースから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は [XSLT/XML](https://globanet.com/xslt-xml) コネクタを提供し、XSLT (Extensible Style sheet Language Transformations) を使用して作成されたファイルを、MICROSOFT 365 にインポートできる他のファイル形式 (HTML やテキストなど) に変換する迅速な開発を可能にしています。 コネクタは、アイテムのコンテンツを XSLT/XML ソースから電子メール メッセージ形式に変換し、変換されたアイテムを Microsoft 365 メールボックスにインポートします。

XSLT/XML データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 XSLT/XML コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-xsltxml-data"></a>XSLT/XML データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の XSLT/XML ソース データをアーカイブするプロセスについて説明します。

![XSLT/XML データのアーカイブ ワークフロー](../media/XSLT-XMLConnectorWorkflow.png)

1. 組織は XSLT/XML ソースと共同で XSLT/XML サイトを設定および構成します。

2. 24 時間ごとに、XSLT/XML ソースからのチャット メッセージが Globanet Merge1 サイトにコピーされます。 コネクタは、コンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する XSLT/XML コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。 ユーザー メールボックスに **XSLT/XML** という名前の受信トレイ フォルダーに新しいサブフォルダーが作成され、メッセージ アイテムがフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべてのメッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 このアカウントは、手順 1 でコネクタを作成するときにサインインします。

- 手順 1 で XSLT/XML コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-an-xsltxml-connector"></a>手順 1: XSLT/XML コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの **Data Connectors** にアクセスし、XSLT/XML データ用のコネクタを作成することです。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ XSLT/XML] に **移動**  >  **してクリックします**。

2. **[XSLT/XML 製品の説明]** ページで、[新しいコネクタの **追加] をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-an-xsltxml-connector"></a>手順 2: XSLT/XML コネクタを構成する

2 番目の手順は、Merge1 サイトで XSLT/XML コネクタを構成することです。 Globanet Merge1 サイトで XSLT/XML コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)」を参照してください。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

1. ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

2. **[XSLT/XML ユーザーを Microsoft 365 ユーザーに** マップする] ページで、ユーザーの自動マッピングを有効にします。 XSLT/XML アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

3. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-xsltxml-connector"></a>手順 4: XSLT/XML コネクタを監視する

XSLT/XML コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブを** クリックし **、XSLT/XML** コネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
