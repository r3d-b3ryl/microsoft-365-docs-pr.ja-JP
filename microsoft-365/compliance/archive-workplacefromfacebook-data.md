---
title: Microsoft 365 の Facebook データから Workplace をアーカイブするコネクタをセットアップする
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
description: 管理者は、Globanet の Merge1 サイトにアーカイブされている Facebook から Microsoft 365 に Workplace からデータをインポートおよびアーカイブするコネクタを設定できます。 コネクタをセットアップするには、Globanet を操作する必要があります このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 843e758430b1fe05ac2977c5a06f12838c81cd42
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923385"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Facebook データから Workplace をアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Workplace から Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は[](https://globanet.com/workplace/)、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Facebook コネクタからの Workplace を提供します。 コネクタは、チャット、添付ファイル、投稿、ビデオなどのコンテンツを Workplace から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Workplace データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Facebook コネクタから Workplace を使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Facebook データからの Workplace のアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Workplace データをアーカイブするプロセスについて説明します。

![Facebook データからの Workplace のアーカイブ ワークフロー](../media/WorkplaceConnectorWorkflow.png)

1. 組織は、Facebook の Workplace を使用して Workplace サイトを設定および構成します。

2. 24 時間に 1 回、Workplace のアイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、これらのアイテムのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成した Facebook コネクタからの Workplace は、毎日 Globanet Merge1 に接続し、Workplace アイテムを Microsoft クラウド内の安全な Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 Facebook の Workplace という名前の **受信** トレイ フォルダー内にサブフォルダーが作成され、Workplace アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Workplace アイテムには、このプロパティが含まれているので、すべてのチャットまたは参加者のメール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- コンプライアンスと電子情報開示の目的で API を介して Workplace からデータを取得するカスタム https://my.workplace.com/work/admin/apps/ 統合を作成します。

   統合を作成すると、Workplace プラットフォームは、認証に使用されるトークンを生成するために使用される一意の資格情報のセットを生成します。 これらのトークンは、手順 2 の Facebook コネクタ構成ウィザードの Workplace で使用されます。 アプリケーションを作成する方法の詳細な手順については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

- 手順 1 で Facebook コネクタから Workplace を作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>手順 1: Facebook コネクタから Workplace をセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、Workplace データ用のコネクタを作成することです。 

1. [Facebook からデータ コネクタ Workplace] に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[データ  >  **コネクタ] をクリックします**。

2. [Facebook 製品 **の説明からのワークプレース** ] ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトの Facebook コネクタから Workplace を構成する

2 番目の手順は、Merge1 サイトの Facebook コネクタから Workplace を構成することです。 Facebook コネクタから Workplace を構成する方法については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。 Workplace アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>手順 4: Facebook コネクタから Workplace を監視する

Facebook コネクタから Workplace を作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し **、Facebook** コネクタから Workplace を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。