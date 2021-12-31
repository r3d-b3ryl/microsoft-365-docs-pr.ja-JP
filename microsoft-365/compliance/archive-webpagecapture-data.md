---
title: Web ページ のデータをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、Web ページ キャプチャ データをインポートおよびアーカイブするコネクタを Veritas からインポートおよびアーカイブMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: de6d00c9835f850dfef779cbff207694ffddd716
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2021
ms.locfileid: "61643398"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Web ページ データをアーカイブするコネクタをセットアップする

ページ内の Veritas コネクタをMicrosoft 365 コンプライアンス センター、Web ページからユーザー のメールボックスにデータをインポートしてアーカイブMicrosoft 365します。 Veritas は、特定の [Web](https://globanet.com/webpage-capture) サイトまたはドメイン全体の特定の Web ページ (およびそれらのページ上のリンク) をキャプチャする Web ページ キャプチャ コネクタを提供します。 コネクタは、Web ページのコンテンツを PDF、PNG、またはカスタム ファイル形式に変換し、変換されたファイルを電子メール メッセージに添付し、それらの電子メール アイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Web ページのコンテンツをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー Microsoft 365保持ラベルなどのコンプライアンス機能を適用できます。 Web ページ キャプチャ コネクタを使用して、組織が政府機関および規制Microsoft 365に準拠し、データをインポートおよびアーカイブできます。

## <a name="overview-of-archiving-webpage-data"></a>Web ページ データのアーカイブの概要

次の概要では、コネクタを使用して Web ページ のコンテンツをアーカイブするプロセスについて説明Microsoft 365。

![Web ページ データのアーカイブ ワークフロー。](../media/WebPageCaptureConnectorWorkflow.png)

1. 組織は Web ページ ソースと一緒に Web ページ キャプチャ サイトを設定および構成します。

2. 24 時間に 1 回、Web ページのソース アイテムが Veritas Merge1 サイトにコピーされます。 コネクタは、Web ページのコンテンツを電子メール メッセージに変換して添付します。

3. Microsoft 365 コンプライアンス センター で作成した Web ページ キャプチャ コネクタは、毎日 Veritas Merge1 サイトに接続し、Web ページアイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Web ページ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 [Web ページ キャプチャ] という名前の **受信** トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Web ページアイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての Web ページ アイテムには、このプロパティが含まれます。このプロパティには、手順 2 で Web ページ キャプチャ コネクタを構成するときに提供される電子メール アドレスが [入力されます](#step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site)。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- Veritas サポートを使用して、Web ページ アイテムを変換するカスタム ファイル形式を設定する必要があります。 詳細については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。

- 手順 1 で Web ページ キャプチャ コネクタを作成し (および手順 3 で完了する) ユーザーは、Web ページのメールボックスインポートエクスポートの役割に割り当てる必要Exchange Online。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-webpage-capture-connector"></a>手順 1: Web ページ キャプチャ コネクタをセットアップする

最初の手順は、データ コネクタ **にアクセス** し、Web ページ ソース データのコネクタを作成することです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) の Web ページ キャプチャ] に移動し、[データ **コネクタ**  >  **] をクリックします**。

2. [Web **ページ キャプチャ製品の説明]** ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Web ページ キャプチャ コネクタを構成する

2 番目の手順は、Veritas Merge1 サイトで Web ページ キャプチャ コネクタを構成することです。 Web ページ キャプチャ コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [Web **ページ のキャプチャ ユーザーをユーザーにMicrosoft 365]** ページで、ユーザーの自動マッピングを有効にします。 Web ページ キャプチャ アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-webpage-capture-connector"></a>手順 4: Web ページ キャプチャ コネクタを監視する

Web ページ キャプチャ コネクタを作成した後、コネクタの状態を [Web ページ] Microsoft 365 コンプライアンス センター。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し **、[Web** ページ キャプチャ コネクタ] を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。