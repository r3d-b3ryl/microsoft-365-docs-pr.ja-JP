---
title: Microsoft 365 でSkype for Business データをアーカイブするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Microsoft Purview コンプライアンス ポータルでコネクタを設定して使用して、Skype for Businessから Microsoft 365 にデータをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: 4301519561c75d4c76cdd47b7adae544f5170585
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632873"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>Skype for Business データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Skype for Business プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には[、](https://www.veritas.com/en/au/insights/merge1/skype-for-business)サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらの項目を Microsoft 365 にインポートするように構成されたSkype for Business コネクタが用意されています。 コネクタは、ユーザー間のメッセージ、常設チャット、会議メッセージなどのコンテンツをSkype for Businessから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Skype for Businessデータがユーザー メールボックスに格納されたら、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 Skype for Business コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-skype-for-business-data"></a>Skype for Business データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 でSkype for Business データをアーカイブするプロセスについて説明します。

![Skype for Business データのアーカイブ ワークフロー。](../media/SkypeforBusinessConnectorWorkflow.png)

1. 組織はSkype for Businessと連携して、Skype for Business サイトを設定および構成します。

2. 24 時間に 1 回、Skype for Business項目が Veritas Merge1 サイトにコピーされます。 また、コネクタはSkype for Businessアイテムを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成するSkype for Business コネクタは、毎日 Veritas Merge1 サイトに接続し、Skype for Business コンテンツを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup). で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 **Skype for Business** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべてのSkype for Businessアイテムには、このプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- Microsoft コネクタの Merge1 アカウントを作成します。 これを行うには、 [Veritas カスタマー サポート](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 でSkype for Business コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-skype-for-business-connector"></a>手順 1: Skype for Business コネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ**] ページにアクセスし、Skype for Business データ用のコネクタを作成します。

1. **データ コネクタ** > に<https://compliance.microsoft.com>移動してクリック **しますSkype for Business**。

2. **Skype for Business** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトでSkype for Businessを構成する

2 番目の手順では、Veritas Merge1 サイトでSkype for Business コネクタを構成します。 Skype for Business コネクタを構成する方法については、「[Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [**ユーザーを Microsoft 365 ユーザーにマップSkype for Business**] ページで、自動ユーザー マッピングを有効にします。 Skype for Business項目 *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-skype-for-business-connector"></a>手順 4: Skype for Business コネクタを監視する

Skype for Business コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com/> ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [**コネクタ**] タブをクリックし、**コネクタに** 関するプロパティと情報を含むポップアップ ページを表示するSkype for Business コネクタを選択します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
