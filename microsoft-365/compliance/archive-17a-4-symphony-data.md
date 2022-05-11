---
title: Microsoft 365でデータをアーカイブするためのシンフォニー DataParser コネクタを設定する
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
description: 17a-4 のシンフォニー DataParser コネクタを設定して使用して、Microsoft 365でシンフォニー データをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: 694a23660c035980d10b7bf36228b7c081997949
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65318018"
---
# <a name="set-up-a-connector-to-archive-data-from-symphony"></a>シンフォニーからデータをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

17a-4 LLC の[シンフォニー DataParser](https://www.17a-4.com/Symphony-dataparser/) を使用して、Microsoft 365組織内のユーザー メールボックスに対して、シンフォニー通信データをインポートおよびアーカイブします。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらの項目をMicrosoft 365にインポートするように構成された、シンフォニー コネクタが含まれています。 シンフォニー DataParser コネクタは、シンフォニー データを電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザー メールボックスにインポートします。

シンフォニー データをユーザー メールボックスに格納した後は、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどのMicrosoft Purview機能を適用できます。 Microsoft 365でデータをインポートおよびアーカイブするために、シンフォニー コネクタを使用すると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-symphony-data"></a>シンフォニー データのアーカイブの概要

次の概要では、データ コネクタを使用してMicrosoft 365のシンフォニー データをアーカイブするプロセスについて説明します。

![17a から 4 の、シンフォニー データのアーカイブ ワークフロー。](../media/SymphonyDataParserConnectorWorkflow.png)

1. 組織は 17a-4 と連携して、シンフォニー DataParser を設定および構成します。

2. 定期的に、シンフォニーアイテムは DataParser によって収集されます。 DataParser では、メッセージの内容も電子メール メッセージ形式に変換されます。

3. Microsoft Purview コンプライアンス ポータルで作成したシンフォニー DataParser コネクタは DataParser に接続し、メッセージを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. ユーザー メールボックスに **、シンフォニー DataParser** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、そのフォルダーにシンフォニーアイテムがインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべてのシンフォニー項目には、すべての参加者の電子メール アドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- Microsoft コネクタの DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC](https://www.17a-4.com/contact/) にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で(手順 3 で完了した) シンフォニー DataParser コネクタを作成するユーザーには、データ コネクタ管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この 17a-4 データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境で使用できます。 サード パーティ製のアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purviewおよびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a>手順 1: シンフォニー DataParser コネクタを設定する

最初の手順では、コンプライアンス ポータルの [データ コネクタ] ページにアクセスし、シンフォニー データ用の 17a-4 コネクタを作成します。

1. **Data** **connectorsSymphony** >  DataParser に<https://compliance.microsoft.com>移動してクリックします。

2. **[シンフォニー DataParser**] 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. 17a-4 アカウントにサインインし、シンフォニー DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-symphony-dataparser-connector"></a>手順 2: シンフォニー DataParser コネクタを構成する

17a-4 サポートと連携して、シンフォニー DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

シンフォニー DataParser コネクタは、Microsoft 365にデータをインポートする前に、ユーザーをMicrosoft 365電子メール アドレスに自動的にマップします。

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a>手順 4: シンフォニー DataParser コネクタを監視する

シンフォニー DataParser コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com> ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、作成した[シンフォニー DataParser] コネクタを選択して、コネクタに関するプロパティと情報を含むポップアップ ページを表示します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
