---
title: Microsoft 365の MS SQL データに Cisco Jabber をアーカイブするためのコネクタを設定する
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
description: 管理者は、Microsoft 365の Veritas から MS SQL データに Cisco Jabber をインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 691b27b59b6ade98523f0324e22e0e0cb533fabd
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946750"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>MS SQL データに Cisco Jabber をアーカイブするためのコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Cisco Jabber プラットフォームからMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には、1 対 1 のチャット メッセージやグループ チャットなど、Jabber の MS SQL Databaseからアイテムをキャプチャし、それらのアイテムをMicrosoft 365にインポートするように構成された [Cisco Jabber](https://globanet.com/jabber/) コネクタが用意されています。 コネクタは、Cisco Jabber の MS SQL Databaseからデータを取得し、処理し、コンテンツをユーザーの Cisco Jabber アカウントから電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザーのメールボックスにインポートします。

Cisco Jabber データをユーザー メールボックスに格納した後は、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft Purview 機能を適用できます。 Cisco Jabber コネクタを使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けるのに役立ちます。

## <a name="overview-of-archiving-cisco-jabber-data"></a>Cisco Jabber データのアーカイブの概要

次の概要では、コネクタを使用して、Microsoft 365の MS SQL データに Cisco Jabber をアーカイブするプロセスについて説明します。

![Cisco Jabber データのアーカイブ ワークフロー。](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 組織は Cisco と連携して、MS SQL Databaseで Cisco Jabber を設定し、構成します。

2. 24 時間に 1 回、Cisco Jabber アイテムは MS SQL Databaseから Veritas Merge1 サイトにコピーされます。 また、コネクタは、チャット メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成した Cisco Jabber コネクタは、毎日 Veritas Merge1 サイトに接続され、アイテムを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. コネクタとしての自動ユーザー マッピングでは、[手順 3](#step-3-map-users-and-complete-the-connector-setup) で説明した *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。 **MS SQLの Cisco Jabber** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Cisco Jabber アイテムには、すべての参加者の電子メール アドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1. でコネクタを作成する前に、Jabber アイテムを取得する MS SQL Databaseを設定します。 手順 2. で Cisco Jabber コネクタを構成するときに、MS SQL Databaseの接続設定を指定します。 詳細については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)参照してください。

- 手順 1 で Cisco Jabber コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>手順 1: MS SQL コネクタで Cisco Jabber を設定する

最初の手順では、コンプライアンス ポータルで **Data Connectors** にアクセスし、MS SQL データに Cisco Jabber 用のコネクタを作成します。

1. MS SQLで [https://compliance.microsoft.com](https://compliance.microsoft.com/)**Data connectorsCisco** >  **Jabber に** 移動してクリックします。

2. MS SQL製品の説明ページ **の Cisco Jabber** で、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトの MS SQL コネクタで Cisco Jabber を構成する

2 番目の手順は、Veritas Merge1 サイトの MS SQL コネクタで Cisco Jabber を構成することです。 MS SQL コネクタで Cisco Jabber を構成する方法については、「[Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [**MS SQL ユーザーをユーザーにマップする**] ページMicrosoft 365、自動ユーザー マッピングを有効にします。 MS SQLアイテムの Cisco Jabber には、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>手順 4: Cisco Jabber コネクタを監視する

MS SQL コネクタで Cisco Jabber を作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [**コネクタ**] タブをクリックし、**MS SQL コネクタの Cisco Jabber** を選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
