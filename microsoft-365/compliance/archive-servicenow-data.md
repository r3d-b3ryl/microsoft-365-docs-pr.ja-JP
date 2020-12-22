---
title: Microsoft 365 で ServiceNow データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に ServiceNow データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 4139e66cc1554b7a7306c6076fd8475fe47f5cf5
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722987"
---
# <a name="set-up-a-connector-to-archive-servicenow-data-preview"></a>ServiceNow データをアーカイブするコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ServiceNow プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は、サード パーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートする [ServiceNow](https://globanet.com/servicenow/) コネクタを提供します。 コネクタは、ServiceNow からのライブ メッセージ、添付ファイル、投稿などのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

ServiceNow データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 ServiceNow コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-servicenow-data"></a>ServiceNow データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の ServiceNow データをアーカイブするプロセスについて説明します。

![ServiceNow データのアーカイブ ワークフロー](../media/ServiceNowConnectorWorkflow.png)

1. 組織は ServiceNow と共同で ServiceNow サイトをセットアップおよび構成します。

2. 24 時間ごとに、ServiceNow アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、ServiceNow アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する ServiceNow コネクタは、毎日 Globanet Merge1 サイトに接続し、ServiceNow コンテンツを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 ServiceNow という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての ServiceNow アイテムにはこのプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- ServiceNow アカウントからデータを取得する ServiceNow アプリケーションを作成します。 アプリケーションの作成に関する詳しい手順については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。

- 手順 1 で ServiceNow コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-servicenow-connector"></a>手順 1: ServiceNow コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、ServiceNow データのコネクタを作成することです。

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **ServiceNow**.

2. **ServiceNow 製品の説明** ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-servicenow-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで ServiceNow を構成する

2 番目の手順は、Globanet Merge1 サイトで ServiceNow コネクタを構成することです。 ServiceNow コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。

[Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. **[ServiceNow ユーザーを Microsoft 365 ユーザーに** マップする] ページで、ユーザーの自動マッピングを有効にします。 ServiceNow アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-servicenow-connector"></a>手順 4: ServiceNow コネクタを監視する

ServiceNow コネクタを作成すると、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブ** をクリックし **、ServiceNow** コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウト ページを表示します。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
