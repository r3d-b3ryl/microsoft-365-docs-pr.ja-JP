---
title: Microsoft 365 で YouTube データをアーカイブするコネクタをセットアップする
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
description: 管理者は、YouTube データを Veritas から Microsoft 365 にインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、電子情報開示、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 0441299c7c0d58855685393526504e2e355343ad
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328233"
---
# <a name="set-up-a-connector-to-archive-youtube-data"></a>YouTube データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、YouTube から Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas は、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたコネクタを提供します。 コネクタは、チャット、添付ファイル、タスク、メモ、投稿などのコンテンツを YouTube から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

YouTube データをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 YouTube コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-youtube-data"></a>YouTube データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の YouTube データをアーカイブするプロセスについて説明します。

![YouTube データのアーカイブ ワークフロー。](../media/YouTubeConnectorWorkflow.png)

1. 組織は YouTube と共同で YouTube サイトを設定および構成します。

2. 24 時間に 1 回、YouTube アイテムは Veritas Merge1 サイトにコピーされます。 また、コネクタは YouTube アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成した YouTube コネクタは、毎日 Veritas Merge1 サイトに接続し、YouTube コンテンツを Microsoft クラウドの安全な Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **YouTube** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての YouTube アイテムにはこのプロパティが含まれるので、アイテムのすべての参加者のメール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/form/requestacall/ms-connectors-contact)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- YouTube アカウントからデータを取得する YouTube アプリケーションを作成します。 アプリケーションの作成の手順については、「Merge1 サードパーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)。

- 手順 1 で YouTube コネクタを作成し (手順 3 で完了する) ユーザーには、データ コネクタ管理者の役割を割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「Microsoft 365 コンプライアンス センターのアクセス許可」の「カスタム役割グループの作成」 [セクションを参照してください](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

## <a name="step-1-set-up-the-youtube-connector"></a>手順 1: YouTube コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、YouTube データ用のコネクタを作成することです。

1. [データ コネクタ <https://compliance.microsoft.com> YouTube] **に移動し、[データ コネクタ** > **] をクリックします**。

2. **[YouTube 製品の説明**] ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-youtube-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで YouTube を構成する

2 番目の手順は、Veritas Merge1 サイトで YouTube コネクタを構成することです。 YouTube コネクタを構成する方法の詳細については、「Merge1 サード パーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20YouTube%20User%20Guide.pdf)。

[ファイルの **保存と&完了]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [ **YouTube ユーザーを Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。 YouTube アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-youtube-connector"></a>手順 4: YouTube コネクタを監視する

YouTube コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側のナビゲーション <https://compliance.microsoft.com/> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、 **YouTube** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
