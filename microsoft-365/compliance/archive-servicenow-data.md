---
title: Microsoft 365で ServiceNow データをアーカイブするコネクタを設定する
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
description: 管理者は、Veritas から Microsoft 365 に ServiceNow データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 775838210a6809d03643ecc4d042398fadb9ed69
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317828"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a>ServiceNow データをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、ServiceNow プラットフォームからMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には、サード パーティのデータ ソースからアイテムをキャプチャし、それらの項目をMicrosoft 365にインポートする [ServiceNow](https://globanet.com/servicenow/) コネクタが用意されています。 コネクタは、ライブ メッセージ、添付ファイル、投稿などのコンテンツを ServiceNow から電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザー メールボックスにインポートします。

ServiceNow データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどのMicrosoft Purview機能を適用できます。 ServiceNow コネクタを使用してMicrosoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-servicenow-data"></a>ServiceNow データのアーカイブの概要

次の概要では、コネクタを使用して ServiceNow データをMicrosoft 365にアーカイブするプロセスについて説明します。

![ServiceNow データのアーカイブ ワークフロー。](../media/ServiceNowConnectorWorkflow.png)

1. 組織は ServiceNow と連携して、ServiceNow サイトを設定および構成します。

2. 24 時間に 1 回、ServiceNow アイテムは Veritas Merge1 サイトにコピーされます。 また、コネクタは ServiceNow アイテムを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成した ServiceNow コネクタは、毎日 Veritas Merge1 サイトに接続し、ServiceNow コンテンツを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup). で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 **ServiceNow** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての ServiceNow アイテムにはこのプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- ServiceNow アカウントからデータをフェッチする ServiceNow アプリケーションを作成します。 アプリケーションの作成に関する詳細な手順については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)参照してください。

- 手順 1 で ServiceNow コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティ製のアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purviewおよびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-servicenow-connector"></a>手順 1: ServiceNow コネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、ServiceNow データ用のコネクタを作成します。

1. **Data connectorsServiceNow** >  に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **ServiceNow** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-servicenow-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで ServiceNow を構成する

2 番目の手順では、Veritas Merge1 サイトで ServiceNow コネクタを構成します。 ServiceNow コネクタを構成する方法の詳細については、「 [Merge1 Third-Party Connectors ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)参照してください。

[ **保存&完了** ] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. **[ServiceNow ユーザーをMicrosoft 365ユーザーにマップ** する] ページで、自動ユーザー マッピングを有効にします。 ServiceNow アイテム *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-servicenow-connector"></a>手順 4: ServiceNow コネクタを監視する

ServiceNow コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **ServiceNow** コネクタを選択してポップアップ ページを表示します。このページには、コネクタに関するプロパティと情報が表示されます。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。