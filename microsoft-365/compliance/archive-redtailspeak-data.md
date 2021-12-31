---
title: コネクタをセットアップして、赤い尾をアーカイブする データをスピー Microsoft 365
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
description: 管理者は、Red tail Speak データを Veritas から他のユーザーにインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: bce266bebd38e49e8ad756dc4100050694bc5d8c
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643614"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Redtail Speak データをアーカイブするコネクタをセットアップする

Redtail Speak to user mailboxs からデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センター内の Veritas コネクタを使用して、Microsoft 365します。 Veritas は [、Redtail](https://globanet.com/redtail/) からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された Redtail Speak コネクタを提供します。 コネクタはコンテンツを Redtail Speak から電子メール メッセージ形式に変換し、それらのアイテムをユーザーのメールボックスにインポートMicrosoft 365。

Redtail Speak データをユーザー のメールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルMicrosoft 365コンプライアンス機能を適用できます。 Redtail Speak コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Redtail Speak データのアーカイブの概要

次の概要では、コネクタを使用して Redtail Speak データをアーカイブするプロセスについて説明Microsoft 365。

![Redtail Speak データのアーカイブ ワークフロー。](../media/RedtailSpeakConnectorWorkflow.png)

1. 組織は Redtail Speak を使用して、メッセージが Redtail Speak から組織の SFTP サーバーに毎日転送される SMTP ゲートウェイを設定および構成します。

2. 24 時間に 1 回、Redtail Speak アイテムが Veritas Merge1 サイトにコピーされます。 また、コネクタは Redtail Speak アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Redtail Speak コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Redtail Speak アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての Redtail Speak アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 2 では、組織の SFTP サーバーを指定する必要があります。 この手順は、Veritas Merge1 が SFTP を介して Redtail Speak データを収集するために接続するために必要です。

- 手順 1 で Redtail Speak Importer コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの [データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定では、既定では、Exchange Onlineグループには割り当てられていない。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>手順 1: Redtail Speak コネクタをセットアップする

最初の手順は、アプリの[データ コネクタ] ページにアクセスし、redtail Speak Microsoft 365 コンプライアンス センターコネクタを作成することです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) ] に移動 **して[Redtail** &gt; **Speak] を選択します**。

2. Redtail **Speak 製品の説明ページ** で、[新しいコネクタの **追加] を選択します**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **選択します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Redtail Speak コネクタを構成する

2 番目の手順は、Merge1 サイトで Redtail Speak コネクタを構成することです。 Redtail Speak コネクタを構成する方法については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。

[ファイルの保存と **&完了**] を選択すると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。

1. [ユーザーを **ユーザーに読み上Microsoft 365する**] ページで、自動ユーザー マッピングを有効にします。 Redtail Speak アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] を選択し、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>手順 4: Redtail Speak コネクタを監視する

Redtail Speak コネクタを作成した後は、コネクタの状態を [メッセージ] ページMicrosoft 365 コンプライアンス センター。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで **[データ コネクタ]** に移動して選択します。

2. [コネクタ **] タブを選択** し **、Redtail Speak コネクタを** 選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が表示されます。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクを選択して、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。