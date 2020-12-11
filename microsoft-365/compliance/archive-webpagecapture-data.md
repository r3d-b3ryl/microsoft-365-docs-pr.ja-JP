---
title: Microsoft 365 で Web ページ データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365 の Globanet から Web ページ キャプチャ データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619823"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>コネクタを設定して Web ページ データをアーカイブする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Web ページから Microsoft 365 組織のユーザー メールボックスにデータをインポートしてアーカイブします。 Globanet は、 [特定の Web サイト](https://globanet.com/webpage-capture) またはドメイン全体の特定の Web ページ (およびそれらのページ上のリンク) をキャプチャする Web ページ キャプチャ コネクタを提供します。 コネクタは、Web ページのコンテンツを PDF、PNG、またはカスタム ファイル形式に変換し、変換されたファイルを電子メール メッセージに添付し、それらの電子メール アイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Web ページのコンテンツがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Web ページ キャプチャ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-webpage-data"></a>Web ページ データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Web ページ コンテンツをアーカイブするプロセスについて説明します。

![Web ページ データのアーカイブ ワークフロー](../media/WebPageCaptureConnectorWorkflow.png)

1. 組織は、Web ページ ソースと一緒に Web ページ キャプチャ サイトを設定および構成します。

2. 24 時間ごとに、Web ページソースのアイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、Web ページのコンテンツを電子メール メッセージに変換して添付します。

3. Microsoft 365 コンプライアンス センターで作成する Web ページ キャプチャ コネクタは、毎日 Globanet Merge1 サイトに接続し、Web ページアイテムを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Web ページ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 ユーザーメールボックスに Web ページ キャプチャという名前の **受信** トレイ フォルダー内のサブフォルダーが作成され、Web ページアイテムがフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Web ページ アイテムには、このプロパティが含まれます。このプロパティには、手順 2 で Web ページ キャプチャ コネクタを構成するときに提供される電子メール アドレスが [設定されます](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact/)。 このアカウントは、手順 1 でコネクタを作成するときにサインインします。

- Web ページアイテムを変換するカスタム ファイル形式を設定するには、Globanet サポートと一緒に作業する必要があります。 詳細については、以下の「Merge1 サード パーティ コネクタ ユーザー ガイド」を参照してください。 

- 手順 1 で Web ページ キャプチャ コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-webpage-capture-connector"></a>手順 1: Web ページ キャプチャ コネクタをセットアップする

最初の手順は、データ コネクタにアクセス **し、Web** ページ ソース データのコネクタを作成することです。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタの Web ページ の **キャプチャ] に**  >  **移動してクリックします**。

2. [Web **ページ のキャプチャ製品の** 説明] ページで、[コネクタの追加 **] をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Web ページ キャプチャ コネクタを構成する

2 番目の手順は、Globanet Merge1 サイトで Web ページ キャプチャ コネクタを構成することです。 Web ページ キャプチャ コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [ **ユーザーを Microsoft 365** ユーザーにマップする] ページで、ユーザーの自動マッピングを有効にします。 Web ページ のキャプチャ アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-webpage-capture-connector"></a>手順 4: Web ページ キャプチャ コネクタを監視する

Web ページ キャプチャ コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブを** クリックし **、Web** ページ キャプチャ コネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
