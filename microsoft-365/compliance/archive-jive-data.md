---
title: コネクタをセットアップして、データ内の Jive データをアーカイブMicrosoft 365
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
description: 管理者は、Veritas から Jive データをインポートおよびアーカイブするコネクタを、Microsoft 365。 このコネクタを使用すると、Microsoft 365 でサード パーティデータをアーカイブして、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: 6133073227e60a0a6ba9022b4b6cac59f85157e6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313273"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>Jive データをアーカイブするコネクタをセットアップする

グループ内の Veritas コネクタをMicrosoft 365 コンプライアンス センター、コラボレーション プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。 Veritas には、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Jive](https://globanet.com/jive/) コネクタが提供されています。 コネクタは、電子メール メッセージ、チャット、添付ファイルなどのコンテンツをユーザーの Jive アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Jive データをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Jive コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-jive-data"></a>Jive データのアーカイブの概要

次の概要では、コネクタを使用して Jive データをアーカイブするプロセスについて説明Microsoft 365。

![Jive データのアーカイブ ワークフロー。](../media/JiveConnectorWorkflow.png)

1. 組織は Jive と一緒に Jive サイトをセットアップおよび構成します。

2. 24 時間に 1 回、Jive のアイテムが Veritas Merge1 サイトにコピーされます。 コネクタは、Jive アイテムのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成する Jive コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にコンテンツを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Jive** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Jive アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 で Jive コネクタを作成し (手順 3 で完了する) ユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-jive-connector"></a>手順 1: Jive コネクタをセットアップする

最初の手順は、アプリケーションの [データ コネクタ] ページにアクセスし、Microsoft 365 コンプライアンス センターコネクタを作成することです。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/)、[**データ コネクタ****Jive]** >  をクリックします。

2. [ **Jive 製品の説明]** ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-jive-connector"></a>手順 2: Jive コネクタを構成する

2 番目の手順は、Merge1 サイトで Jive コネクタを構成することです。 Jive コネクタを構成する方法の詳細については、「Merge1 サード パーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザー **をユーザーにマップMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。 Jive アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-jive-connector"></a>手順 4: Jive コネクタを監視する

Jive コネクタを作成した後、コネクタの状態を [コネクタ] ページでMicrosoft 365 コンプライアンス センター。

1. 左側のナビゲーション [https://compliance.microsoft.com](https://compliance.microsoft.com) で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、 **Jive コネクタを選択** して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。