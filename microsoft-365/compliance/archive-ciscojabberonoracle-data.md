---
title: Cisco Jabber を Oracle データにアーカイブするコネクタをセットアップMicrosoft 365
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
description: Oracle の Cisco Jabber からデータをインポートおよびアーカイブするために、Microsoft 365 コンプライアンス センター でコネクタを設定して使用する方法について説明Microsoft 365。
ms.openlocfilehash: d58d015e94050bc82b427ba450314b7bb447d4d1
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320649"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data"></a>Oracle データで Cisco Jabber をアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センター の Veritas コネクタを使用して、Oracle プラットフォーム上の Cisco Jabber から組織のユーザー メールボックスにデータをインポートMicrosoft 365します。 Veritas は、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された、Oracle コネクタ上の Cisco [Jabber](https://www.veritas.com/insights/merge1/jabber) を提供します。 コネクタは、ファイルやファイル操作、コメント、共有コンテンツなどのコンテンツを Oracle の Cisco Jabber から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Oracle データの Cisco Jabber がユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Oracle コネクタで Cisco Jabber を使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Oracle データに対する Cisco Jabber のアーカイブの概要

次の概要では、コネクタを使用して、Cisco Jabber を Oracle データにアーカイブするプロセスMicrosoft 365。

![Oracle データに関する Cisco Jabber のアーカイブ ワークフロー。](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. 組織は Oracle の Cisco Jabber と共同で、Oracle サイトで Cisco Jabber をセットアップおよび構成します。

2. 24 時間に 1 回、Oracle アイテムの Cisco Jabber が Veritas Merge1 サイトにコピーされます。 また、コネクタは Oracle アイテムの Cisco Jabber を電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Oracle コネクタ上の Cisco Jabber は、毎日 Veritas Merge1 サイトに接続し、Jabber コンテンツを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 Oracle の Cisco **Jabber** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Jabber アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Merge1 アカウントを作成します。 これを行うには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/en_US)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Oracle コネクタで Cisco Jabber を作成し (手順 3 で完了する) ユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>手順 1: Oracle コネクタで Cisco Jabber をセットアップする

最初の手順は、次のページの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センタージャバー データのコネクタを作成することです。

1. [データ コネクタ<https://compliance.microsoft.com>] に移動 **し、[Oracle] の** >  **[データ コネクタCisco Jabber] をクリックします**。

2. [ **Oracle 製品の説明] ページの [Cisco Jabber** ] で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトの Oracle で Cisco Jabber を構成する

2 番目の手順は、Veritas Merge1 サイトの Oracle コネクタで Cisco Jabber を構成することです。 Oracle コネクタで Cisco Jabber を構成する方法については、「Merge1 サードパーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [Oracle ユーザー **に Cisco Jabber をマップしてユーザーにMicrosoft 365する**] ページで、自動ユーザー マッピングを有効にします。 Oracle アイテムの Cisco Jabber には、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>手順 4: Oracle コネクタで Cisco Jabber を監視する

Oracle コネクタで Cisco Jabber を作成した後は、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com/> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、Oracle コネクタの **Cisco Jabber** を選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
