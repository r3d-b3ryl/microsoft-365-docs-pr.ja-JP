---
title: MS 上の Cisco Jabber をアーカイブするコネクタをセットアップし、SQLデータをMicrosoft 365
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
description: 管理者は、Ms 上の Cisco Jabber をインポートおよびアーカイブするコネクタをセットアップし、SQLで Veritas からデータをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 66f09f2fafcd33d8bc73bdaed61b41354e9633f7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319547"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>MS データで Cisco Jabber をアーカイブするコネクタSQLする

Cisco Jabber プラットフォームからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、組織のユーザー メールボックスMicrosoft 365します。 Veritas は、Jabber の MS SQL Database からアイテム (1:1 チャット メッセージやグループ チャットなど) をキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Cisco Jabber](https://globanet.com/jabber/) コネクタを提供します。 コネクタは、Cisco Jabber の MS SQL Database からデータを取得し、処理し、コンテンツをユーザーの Cisco Jabber アカウントから電子メール メッセージ形式に変換し、Microsoft 365 のユーザーのメールボックスにそれらのアイテムをインポートします。

Cisco Jabber データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Cisco Jabber コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-cisco-jabber-data"></a>Cisco Jabber データのアーカイブの概要

次の概要では、コネクタを使用して、Ms 上の Cisco Jabber をアーカイブし、SQLデータをアーカイブMicrosoft 365。

![Cisco Jabber データのアーカイブ ワークフロー。](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 組織は、Cisco と一緒に MS サーバーで Cisco Jabber をセットアップおよび構成SQL Database。

2. 24 時間に 1 回、Cisco Jabber アイテムは MS SQL Database Veritas Merge1 サイトにコピーされます。 コネクタは、チャット メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成する Cisco Jabber コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage 場所にアイテムを転送します。

4. コネクタとしての自動ユーザー マッピングは、手順 3 で説明した *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 MS SQL の **Cisco Jabber という** 名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにメッセージ アイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての Cisco Jabber アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 でコネクタSQL Databaseする前に、Jabber アイテムを取得する MS ファイルをセットアップします。 手順 2 で Cisco Jabber コネクタSQL Database MS インターフェイスの接続設定を指定します。 詳細については、「 [Merge1 サードパーティ コネクタ ユーザー ガイド」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

- 手順 1 で Cisco Jabber コネクタを作成するユーザー (および手順 3 で完了) には、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>手順 1: MS インターフェイス コネクタで Cisco Jabber をSQLする

最初の手順は、データ のデータ  コネクタにアクセスし、ms Microsoft 365 コンプライアンス センターデータ上に Cisco Jabber 用のコネクタSQLすることです。

1. MS の [[https://compliance.microsoft.com](https://compliance.microsoft.com/)データ コネクタCisco  > **Jabber**] に移動し、[データ コネクタ] SQL。

2. [**MS の Cisco Jabber SQL** 説明] ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトの MS SQLコネクタで Cisco Jabber を構成する

2 番目の手順は、Veritas Merge1 サイトの MS SQLコネクタで Cisco Jabber を構成することです。 Ms SQL コネクタで Cisco Jabber を構成する方法については、「Merge1 サード パーティ コネクタ ユーザー ガイド」[を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザー **をユーザーに割り当SQLする MS Microsoft 365 Cisco Jabber** のマップ] ページで、自動ユーザー マッピングを有効にします。 MS の Cisco Jabber SQLには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>手順 4: Cisco Jabber コネクタを監視する

MS インターフェイス コネクタに Cisco Jabber をSQLした後、コネクタの状態を[コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション [https://compliance.microsoft.com](https://compliance.microsoft.com) で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、MS コネクタの **Cisco Jabber** SQLを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
