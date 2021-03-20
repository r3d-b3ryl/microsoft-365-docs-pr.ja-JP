---
title: Microsoft 365 で Red tail Speak データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Globanet から Microsoft 365 にデータを読み込み、アーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 89b90fd29e089bf61632b22b38e6e10335fda2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906061"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Redtail Speak データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織のユーザー メールボックスに Redtail Speak からデータをインポートおよびアーカイブします。 Globanet は [、Redtail](https://globanet.com/redtail/) からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された Redtail Speak コネクタを提供します。 コネクタはコンテンツを Redtail Speak から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Redtail Speak データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Redtail Speak コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Redtail Speak データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Redtail Speak データをアーカイブするプロセスについて説明します。

![Redtail Speak データのアーカイブ ワークフロー](../media/RedtailSpeakConnectorWorkflow.png)

1. 組織は Redtail Speak を使用して、メッセージが Redtail Speak から組織の SFTP サーバーに毎日転送される SMTP ゲートウェイを設定および構成します。

2. 24 時間に 1 回、Redtail Speak アイテムが Globanet Merge1 サイトにコピーされます。 また、コネクタは Redtail Speak アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成した Redtail Speak コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Redtail Speak アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての Redtail Speak アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 2 では、組織の SFTP サーバーを指定する必要があります。 この手順は、Globanet Merge1 に連絡して SFTP 経由で Redtail Speak データを収集するために必要です。

- 手順 1 で Redtail Speak Importer コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにコネクタを追加するには、この役割が必要です。 この役割は、既定では Exchange Online の役割グループには割り当てられていない。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>手順 1: Redtail Speak コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、Redtail Speak データのコネクタを作成することです。 

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) ] に移動 **して[Redtail** &gt; **Speak] を選択します**。

2. Redtail **Speak 製品の説明ページ** で、[新しいコネクタの **追加] を選択します**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **選択します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Redtail Speak コネクタを構成する

2 番目の手順は、Merge1 サイトで Redtail Speak コネクタを構成することです。 Redtail Speak コネクタを構成する方法については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。

[ファイルの保存&完了]**を選択** すると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。

1. **[Redtail ユーザーを Microsoft 365** ユーザーに読み上げにする] ページで、自動ユーザー マッピングを有効にする。 Redtail Speak アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] を選択し、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>手順 4: Redtail Speak コネクタを監視する

Redtail Speak コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで **[データ コネクタ]** に移動して選択します。

2. [コネクタ **] タブを選択** し **、Redtail Speak コネクタを** 選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が表示されます。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクを選択して、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。