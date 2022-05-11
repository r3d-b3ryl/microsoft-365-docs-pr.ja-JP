---
title: Microsoft 365の Facebook データから Workplace をアーカイブするコネクタを設定する
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
description: 管理者は、Facebook から Workplace からデータをインポートしてアーカイブするコネクタを設定できます。これは、Veritas の Merge1 サイトにアーカイブされ、Microsoft 365に保存されます。 コネクタを設定するには、Veritas を使用する必要がありますこのコネクタを使用すると、Microsoft 365のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して組織のサードパーティ データを管理できます。
ms.openlocfilehash: 63fe30e8d8c264976c496480df056746b7b27ae5
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317042"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Facebook データから Workplace をアーカイブするためのコネクタを設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Workplace から Facebook からMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムをMicrosoft 365にインポートするように構成された [Workplace from Facebook](https://globanet.com/workplace/) コネクタが用意されています。 コネクタは、チャット、添付ファイル、投稿、ビデオなどのコンテンツを Workplace から電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザー メールボックスにインポートします。

Workplace データをユーザー メールボックスに格納した後は、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどのMicrosoft Purview機能を適用できます。 Workplace from Facebook コネクタを使用してMicrosoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Facebook データからの Workplace のアーカイブの概要

次の概要では、コネクタを使用してMicrosoft 365の Workplace データをアーカイブするプロセスについて説明します。

![Facebook データから Workplace のワークフローをアーカイブする。](../media/WorkplaceConnectorWorkflow.png)

1. 組織は Facebook の Workplace と連携して Workplace サイトを設定および構成します。

2. 24 時間に 1 回、Workplace のアイテムが Veritas Merge1 サイトにコピーされます。 コネクタでは、これらのアイテムのコンテンツも電子メール メッセージ形式に変換されます。

3. コンプライアンス ポータルで作成した Workplace from Facebook コネクタは、毎日 Veritas Merge1 に接続し、Workplace アイテムを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. コネクタは、手順 3. で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 **Workplace from Facebook** という名前の受信トレイ フォルダーにサブフォルダーが作成され、Workplace アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべての Workplace アイテムにはこのプロパティが含まれています。このプロパティには、すべてのチャットまたは投稿参加者のメール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- コンプライアンスと電子情報開示の目的で https://my.workplace.com/work/admin/apps/ API を使用して Workplace からデータを取得するためのカスタム統合を作成します。

   統合を作成するときに、Workplace プラットフォームは、認証に使用されるトークンの生成に使用される一意の資格情報のセットを生成します。 これらのトークンは、手順 2. の Workplace from Facebook コネクタ構成ウィザードで使用されます。 アプリケーションを作成する方法の詳細な手順については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)参照してください。

- 手順 1 で Workplace from Facebook コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境でパブリック プレビュー段階にあります。 サード パーティ製のアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft Purviewおよびデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>手順 1: Facebook コネクタから Workplace を設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、Workplace データ用のコネクタを作成します。

1. Facebook から **Data connectorsWorkplace** >  に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **Workplace from Facebook** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Workplace from Facebook コネクタを構成する

2 番目の手順では、Merge1 サイトで Workplace from Facebook コネクタを構成します。 Facebook コネクタから Workplace を構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. [**外部ユーザーを Microsoft 365 ユーザーにマップ** する] ページで、自動ユーザー マッピングを有効にします。 Workplace アイテムには、組織内のユーザーのメール *アドレスを含* む Email というプロパティが含まれています。 コネクタがこのアドレスをMicrosoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>手順 4: Facebook コネクタから Workplace を監視する

Facebook コネクタから Workplace を作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **Workplace from Facebook** ] コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。