---
title: Microsoft 365で Red Tail Speak データをアーカイブするようにコネクタを設定する
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
description: 管理者は、Red tail Speak データを Veritas からMicrosoft 365にインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 46b9646fee78fa0589a9af41db35cf79a71e508f
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64994570"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Redtail Speak データをアーカイブするコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルで Veritas コネクタを使用して、Redtail Speak からデータをインポートし、Microsoft 365組織内のユーザー メールボックスにアーカイブします。 Veritas には、Redtail からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された [Redtail Speak](https://globanet.com/redtail/) コネクタが用意されています。 コネクタは、Redtail Speak から電子メール メッセージ形式にコンテンツを変換し、それらのアイテムをMicrosoft 365のユーザーのメールボックスにインポートします。

Redtail Speak データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 Redtail Speak コネクタを使用してMicrosoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けるのに役立ちます。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Redtail Speak データのアーカイブの概要

次の概要では、コネクタを使用して Redtail Speak データをMicrosoft 365にアーカイブするプロセスについて説明します。

![Redtail Speak データのアーカイブ ワークフロー。](../media/RedtailSpeakConnectorWorkflow.png)

1. 組織は Redtail Speak と連携して、Redtail Speak から組織の SFTP サーバーに毎日メッセージが転送される SMTP ゲートウェイを設定および構成します。

2. 24 時間に 1 回、Redtail Speak アイテムが Veritas Merge1 サイトにコピーされます。 コネクタでは、Redtail Speak アイテムも電子メール メッセージ形式に変換されます。

3. コンプライアンス ポータルで作成した Redtail Speak コネクタは、毎日 Veritas Merge1 サイトに接続され、Microsoft クラウド内の安全なAzure Storage場所にメッセージを転送します。

4. コネクタは、変換された Redtail Speak アイテムを、[手順 3](#step-3-map-users-and-complete-the-connector-setup). の説明に従って自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにインポートします。 **Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Redtail Speak アイテムにはこのプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 2 では、組織の SFTP サーバーを指定する必要があります。 この手順は、Veritas Merge1 が SFTP を介して Redtail Speak データを収集するために連絡できるように必要です。

- 手順 1 で Redtail Speak Importer コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purview およびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>手順 1: Redtail Speak コネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、Redtail Speak データのコネクタを作成します。

1. **データ コネクタ** &gt; **の Redtail Speak** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動して選択します。

2. **Redtail Speak** 製品の説明ページで、[**新しいコネクタの追加**] を選択します。

3. [利用規約] ページ **で** 、[ **同意** する] を選択します。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] を選択します。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Redtail Speak コネクタを構成する

2 番目の手順では、Merge1 サイトで Redtail Speak コネクタを構成します。 Redtail Speak コネクタを構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)参照してください。

**[保存&完了**] を選択すると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング**] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順に従います。

1. [**ユーザーを Microsoft 365 ユーザーに話す**] ページで、自動ユーザー マッピングを有効にします。 Redtail Speak アイテム *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. **[次へ**] を選択し、設定を確認し、[**データ コネクタ**] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>手順 4: Redtail Speak コネクタを監視する

Redtail Speak コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションにある **[データ コネクタ** ] に移動して選択します。

2. [ **コネクタ** ] タブを選択し、 **Redtail Speak** コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が表示されます。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクを選択して、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。