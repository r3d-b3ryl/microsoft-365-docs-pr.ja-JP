---
title: Microsoft 365で XSLT/XML データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365で Veritas から XSLT/XML データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティのデータを管理できます。
ms.openlocfilehash: 92932e3e18c8f43c46cf71e43ec02306d78a2f60
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995736"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>XSLT/XML データをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Web ページ ソースからMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には [XSLT/XML コネクタ](https://globanet.com/xslt-xml)が用意されています。XSLT (拡張可能スタイル シート言語変換) を使用して作成されたファイルを迅速に開発し、XML ファイルを他のファイル形式 (HTML やテキストなど) に変換し、Microsoft 365にインポートできます。 コネクタは、XSLT/XML ソースからアイテムのコンテンツを電子メール メッセージ形式に変換し、変換されたアイテムをMicrosoft 365メールボックスにインポートします。

XSLT/XML データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 XSLT/XML コネクタを使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-xsltxml-data"></a>XSLT/XML データのアーカイブの概要

次の概要では、コネクタを使用して XSLT/XML ソース データをMicrosoft 365にアーカイブするプロセスについて説明します。

![XSLT/XML データのアーカイブ ワークフロー。](../media/XSLT-XMLConnectorWorkflow.png)

1. 組織は XSLT/XML ソースと連携して XSLT/XML サイトを設定および構成します。

2. 24 時間に 1 回、XSLT/XML ソースからのチャット メッセージが Veritas Merge1 サイトにコピーされます。 また、コネクタはコンテンツを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成する XSLT/XML コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全なAzure Storage場所にメッセージを転送します。

4. コネクタは、手順 3. の説明に従って、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。 **XSLT/XML** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべてのメッセージにはこのプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 で XSLT/XML コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-an-xsltxml-connector"></a>手順 1: XSLT/XML コネクタを設定する

最初の手順では、コンプライアンス ポータルで **データ コネクタ** にアクセスし、XSLT/XML データ用のコネクタを作成します。

1. **データ コネクタ** > **XSLT/XML** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **XSLT/XML** 製品の説明ページで、[**新しいコネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-an-xsltxml-connector"></a>手順 2: XSLT/XML コネクタを構成する

2 番目の手順では、Merge1 サイトで XSLT/XML コネクタを構成します。 Veritas Merge1 サイトで XSLT/XML コネクタを構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

1. ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

2. [**XSLT/XML ユーザーをMicrosoft 365ユーザーにマップ** する] ページで、自動ユーザー マッピングを有効にします。 XSLT/XML アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

3. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-xsltxml-connector"></a>手順 4: XSLT/XML コネクタを監視する

XSLT/XML コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **XSLT/XML** コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。