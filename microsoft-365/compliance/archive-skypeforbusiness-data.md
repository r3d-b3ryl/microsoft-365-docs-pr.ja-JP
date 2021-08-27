---
title: コネクタをセットアップして、Skype for BusinessデータをアーカイブMicrosoft 365
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
description: データをインポートおよびアーカイブする方法については、Microsoft 365 コンプライアンス センターでコネクタを設定して使用して、Skype for BusinessからMicrosoft 365。
ms.openlocfilehash: 3f772bfa7b59eac7292cd869aee2688ac1a132b6
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58563109"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a>データをアーカイブするコネクタをSkype for Businessする

サーバーの Veritas コネクタを使用Microsoft 365 コンプライアンス センター、Skype for Business プラットフォームから組織のユーザー メールボックスにデータをインポートMicrosoft 365します。 Veritas には[](https://www.veritas.com/en/au/insights/merge1/skype-for-business)、Skype for Business データ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムをデータ ソースにインポートするように構成された Microsoft 365。 コネクタは、ユーザー間のメッセージ、常設チャット、会議メッセージなどのコンテンツを Skype for Business から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

ユーザー Skype for Businessにデータを保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルMicrosoft 365コンプライアンス機能を適用できます。 アプリケーション コネクタSkype for Business使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-skype-for-business-data"></a>データのアーカイブSkype for Business概要

次の概要では、コネクタを使用してデータをアーカイブするプロセスSkype for Business説明Microsoft 365。

![データのアーカイブ ワークフロー Skype for Businessします。](../media/SkypeforBusinessConnectorWorkflow.png)

1. 組織は、Skype for Businessサイトをセットアップおよび構成するためにSkype for Businessします。

2. 24 時間に 1 回Skype for Businessは Veritas Merge1 サイトにコピーされます。 また、コネクタは、Skype for Businessを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Skype for Business コネクタは、毎日 Veritas Merge1 サイトに接続し、Skype for Business コンテンツを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 [受信トレイ] という名前の **Skype for Business** サブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべてのSkype for Businessには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の Merge1 アカウントを作成します。 これを行うには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Skype for Business コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割は、グループ内の任意の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-the-skype-for-business-connector"></a>手順 1: コネクタをSkype for Businessする

最初の手順は、 [データコネクタ] ページの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センターデータのコネクタをSkype for Businessすることです。

1. に移動し <https://compliance.microsoft.com> 、[**データ コネクタ] を**  >  **クリックSkype for Business。**

2. [製品の **Skype for Business]** ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトSkype for Businessを構成する

2 番目の手順は、Veritas Merge1 サイトSkype for Businessコネクタを構成することです。 コネクタを構成する方法についてはSkype for Business [Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)コネクタ ユーザー ガイドを参照してください。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザーを **ユーザーにSkype for BusinessするMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。 このSkype for Businessには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-skype-for-business-connector"></a>手順 4: コネクタをSkype for Businessする

コネクタコネクタを作成Skype for Business、コネクタの状態を [コネクタ] で表示Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、Skype for Businessコネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。 

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
