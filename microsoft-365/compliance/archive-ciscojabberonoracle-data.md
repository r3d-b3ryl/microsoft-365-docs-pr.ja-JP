---
title: Microsoft 365の Oracle データに Cisco Jabber をアーカイブするためのコネクタを設定する
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
description: Microsoft Purview コンプライアンス ポータルでコネクタを設定して使用して、Oracle 上の Cisco Jabber からMicrosoft 365にデータをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: c7a1172053fa4e403d82dd01bd65ea2ab141dc68
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65318384"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Oracle データに Cisco Jabber をアーカイブするためのコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Oracle プラットフォーム上の Cisco Jabber からMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas は、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらの項目をMicrosoft 365にインポートするように構成された、Oracle コネクタ上の [Cisco Jabber](https://www.veritas.com/insights/merge1/jabber) を提供します。 コネクタは、ファイルやファイル操作、コメント、共有コンテンツなどのコンテンツを Oracle の Cisco Jabber から電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザーのメールボックスにインポートします。

Oracle データの Cisco Jabber がユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどのMicrosoft Purview機能を適用できます。 Oracle コネクタで Cisco Jabber を使用してMicrosoft 365にデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Oracle データに対する Cisco Jabber のアーカイブの概要

次の概要では、コネクタを使用してMicrosoft 365の Oracle データに Cisco Jabber をアーカイブするプロセスについて説明します。

![Oracle データに対する Cisco Jabber のアーカイブ ワークフロー。](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. 組織は、Oracle の Cisco Jabber と連携して、Oracle サイトで Cisco Jabber を設定および構成します。

2. 24 時間に 1 回、Oracle アイテムの Cisco Jabber が Veritas Merge1 サイトにコピーされます。 また、コネクタは、Oracle アイテムの Cisco Jabber を電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成する Oracle コネクタ上の Cisco Jabber は、毎日 Veritas Merge1 サイトに接続し、Jabber コンテンツを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup). で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 Oracle 上の **Cisco Jabber** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべての Jabber アイテムにはこのプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Merge1 アカウントを作成します。 これを行うには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/en_US)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で Oracle コネクタに Cisco Jabber を作成し、手順 3 で完了したユーザーには、Data Connector Admin ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティ製のアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purviewおよびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>手順 1: Oracle コネクタで Cisco Jabber を設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、Jabber データ用のコネクタを作成します。

1. Oracle の **Data connectorsCisco** >  **Jabber に**<https://compliance.microsoft.com>移動してクリックします。

2. Oracle 製品の説明ページ **の Cisco Jabber で** 、[ **コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Oracle で Cisco Jabber を構成する

2 番目の手順は、Veritas Merge1 サイトの Oracle コネクタで Cisco Jabber を構成することです。 Oracle コネクタで Cisco Jabber を構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [**Oracle ユーザーの Cisco Jabber をユーザーにマップする] ページMicrosoft 365**、自動ユーザー マッピングを有効にします。 Oracle アイテムの Cisco Jabber *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>手順 4: Oracle コネクタで Cisco Jabber を監視する

Oracle コネクタで Cisco Jabber を作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com/> ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **Oracle コネクタの Cisco Jabber** を選択して、コネクタのプロパティと情報を含むポップアップ ページを表示します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
