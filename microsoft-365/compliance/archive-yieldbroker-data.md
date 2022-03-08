---
title: データの Yieldbroker データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: 管理者は、Veritas からユーザーに Yieldbroker データをインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 4a3c56659b4229774af6804d1dc3a6f30aa85039
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311817"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Yieldbroker データをアーカイブするコネクタをセットアップする

サーバーの Veritas コネクタを使用Microsoft 365 コンプライアンス センター、Yieldbroker から組織のユーザー メールボックスにデータをインポートMicrosoft 365します。 Veritas は、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された [Yieldbroker](https://globanet.com/yieldbroker/) コネクタをMicrosoft 365。 コネクタは、コンテンツを Yieldbroker から電子メール メッセージ形式に変換し、それらのアイテムをユーザーのメールボックスにインポートMicrosoft 365。

Yieldbroker をユーザー のメールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルMicrosoft 365コンプライアンス機能を適用できます。 Yieldbroker コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-yieldbroker-data"></a>Yieldbroker データのアーカイブの概要

次の概要では、コネクタを使用して、アプリケーション内の Yieldbroker データをアーカイブするMicrosoft 365。

![Yieldbroker データのアーカイブ ワークフロー。](../media/YieldbrokerConnectorWorkflow.png)

1. 組織は Yieldbroker を使用して Yieldbroker サイトを設定および構成します。

2. 24 時間に 1 回、Yieldbroker アイテムは Veritas Merge1 サイトにコピーされます。 コネクタは、コンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Yieldbroker コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの Email プロパティの値を使用して、変換された *Yieldbroker* アイテムを特定のユーザーのメールボックスに [インポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Yieldbroker** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての Yieldbroker には、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Yieldbroker コネクタを作成し 、手順 3 で完了するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-yieldbroker-connector"></a>手順 1: Yieldbroker コネクタをセットアップする

最初の手順は、次のページの [データ コネクタ] ページMicrosoft 365 コンプライアンス センター、Yieldbroker のコネクタを作成します。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) Yieldbroker] **に移動し**、[データ コネクタ&gt;**] をクリックします**。

2. [ **Yieldbroker 製品の説明] ページ** で、[新しいコネクタの **追加] をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Yieldbroker コネクタを構成する

2 番目の手順は、Merge1 サイトで Yieldbroker コネクタを構成することです。 Yieldbroker を構成する方法の詳細については、「Merge1 サード パーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。

1. [**Yieldbroker ユーザーをユーザーにマップMicrosoft 365] ページ** で、自動ユーザー マッピングを有効にします。 Yieldbroker アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-yieldbroker-connector"></a>手順 4: Yieldbroker コネクタを監視する

Yieldbroker コネクタを作成した後は、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション [https://compliance.microsoft.com](https://compliance.microsoft.com/) で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、 **Yieldbroker** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。