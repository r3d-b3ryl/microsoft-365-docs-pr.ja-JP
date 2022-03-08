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
description: 管理者は、Red Tail Speak データを Veritas からユーザーにインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 8c0e3c444bf285f951911a9de6e5ef3480eb6468
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321055"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Redtail Speak データをアーカイブするコネクタをセットアップする

Redtail Speak to user mailboxs からデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センター内の Veritas コネクタを使用して、Microsoft 365します。 Veritas は、Redtail からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された [Redtail](https://globanet.com/redtail/) Speak コネクタを提供します。 コネクタはコンテンツを Redtail Speak から電子メール メッセージ形式に変換し、それらのアイテムをユーザーのメールボックスにインポートMicrosoft 365。

Redtail Speak データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどのコンプライアンス機能Microsoft 365を適用できます。 Redtail Speak コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Redtail Speak データのアーカイブの概要

次の概要では、コネクタを使用して Redtail Speak データをアーカイブするプロセスについて説明Microsoft 365。

![Redtail Speak データのアーカイブ ワークフロー。](../media/RedtailSpeakConnectorWorkflow.png)

1. 組織は Redtail Speak を使用して、メッセージが Redtail Speak から組織の SFTP サーバーに毎日転送される SMTP ゲートウェイを設定および構成します。

2. 24 時間に 1 回、Redtail Speak アイテムが Veritas Merge1 サイトにコピーされます。 また、コネクタは Redtail Speak アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Redtail Speak コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Redtail Speak アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての Redtail Speak アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 2 では、組織の SFTP サーバーを指定する必要があります。 この手順は、Veritas Merge1 が SFTP を介して Redtail Speak データを収集するために接続するために必要です。

- 手順 1 で Redtail Speak Importer コネクタを作成するユーザー (および手順 3 で完了) には、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>手順 1: Redtail Speak コネクタをセットアップする

最初の手順は、アプリの [データ コネクタ] ページにアクセスし、redtail Speak Microsoft 365 コンプライアンス センターコネクタを作成することです。

1. [データ コネクタ] [https://compliance.microsoft.com](https://compliance.microsoft.com/) に移動 **し、[** &gt; **Redtail Speak] を選択します**。

2. [ **Redtail Speak 製品の説明]** ページで、[新しいコネクタの **追加] を選択します**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. コネクタを識別する一意の名前を入力し、[次へ] を選択 **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Redtail Speak コネクタを構成する

2 番目の手順は、Merge1 サイトで Redtail Speak コネクタを構成することです。 Redtail Speak コネクタを構成する方法については、「Merge1 サード パーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。

[ファイルの保存と **&完了**] を選択すると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。

1. [ユーザーを **ユーザーに読み上Microsoft 365する**] ページで、自動ユーザー マッピングを有効にします。 Redtail Speak アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] を選択し、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>手順 4: Redtail Speak コネクタを監視する

Redtail Speak コネクタを作成した後は、コネクタの状態を [メッセージ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション [https://compliance.microsoft.com](https://compliance.microsoft.com/) で **[データ コネクタ]** に移動して選択します。

2. [コネクタ **] タブを選択** し、 **Redtail Speak コネクタを** 選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が表示されます。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクを選択して、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。