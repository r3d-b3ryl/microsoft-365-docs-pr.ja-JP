---
title: Microsoft 365 で Web ページ データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Microsoft 365 の Globanet から Web ページ キャプチャ データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: de1e181670f1efc2e758b666dc3a26337a294ee2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920801"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Web ページ データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Web ページから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は、特定の [Web](https://globanet.com/webpage-capture) サイトまたはドメイン全体の特定の Web ページ (およびそれらのページ上のリンク) をキャプチャする Web ページ キャプチャ コネクタを提供します。 コネクタは、Web ページのコンテンツを PDF、PNG、またはカスタム ファイル形式に変換し、変換されたファイルを電子メール メッセージに添付し、それらの電子メール アイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Web ページのコンテンツをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Web ページ キャプチャ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-webpage-data"></a>Web ページ データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Web ページ コンテンツをアーカイブするプロセスについて説明します。

![Web ページ データのアーカイブ ワークフロー](../media/WebPageCaptureConnectorWorkflow.png)

1. 組織は Web ページ ソースと一緒に Web ページ キャプチャ サイトを設定および構成します。

2. 24 時間に 1 回、Web ページのソース アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、Web ページのコンテンツを電子メール メッセージに変換して添付します。

3. Microsoft 365 コンプライアンス センターで作成した Web ページ キャプチャ コネクタは、毎日 Globanet Merge1 サイトに接続し、Web ページアイテムを Microsoft クラウド内の安全な Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Web ページ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 [Web ページ キャプチャ] という名前の **受信** トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Web ページアイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Web ページ アイテムには、このプロパティが含まれます。このプロパティには、手順 2 で Web ページ キャプチャ コネクタを構成するときに提供される電子メール アドレスが [入力されます](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- Web ページアイテムを変換するカスタム ファイル形式を設定するには、Globanet サポートと一緒に作業する必要があります。 詳細については、「Merge1 サードパーティ コネクタ ユーザー ガイド」を参照してください。 

- 手順 1 で Web ページ キャプチャ コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-webpage-capture-connector"></a>手順 1: Web ページ キャプチャ コネクタをセットアップする

最初の手順は、データ コネクタ **にアクセス** し、Web ページ ソース データのコネクタを作成することです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) の Web ページ キャプチャ] に移動し、[データ **コネクタ**  >  **] をクリックします**。

2. [Web **ページ キャプチャ製品の説明]** ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Web ページ キャプチャ コネクタを構成する

2 番目の手順は、Globanet Merge1 サイトで Web ページ キャプチャ コネクタを構成することです。 Web ページ キャプチャ コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [Web **ページ キャプチャ ユーザーを Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にします。 Web ページ キャプチャ アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-webpage-capture-connector"></a>手順 4: Web ページ キャプチャ コネクタを監視する

Web ページ キャプチャ コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し **、[Web** ページ キャプチャ コネクタ] を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。