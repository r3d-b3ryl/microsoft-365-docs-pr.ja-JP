---
title: TeleMessage ファイルからデータをアーカイブするコネクタをセットアップEnterpriseアーカイブ
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
description: 管理者は、TeleMessage および Number Archiver から SMS および MMS データをインポートおよびアーカイブするコネクタEnterpriseできます。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: be9bb382752fbfd1dfe37666b8b9e0b17a2b5e3f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167512"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Number データをアーカイブするコネクタEnterprise設定する

Microsoft 365 コンプライアンス センター の TeleMessage コネクタを使用して、Enterprise Number Archiver からショート メッセージング サービス (SMS) メッセージ、マルチメディア メッセージング サービス (MMS) メッセージ、チャット メッセージ、音声通話録音、音声通話ログをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、組織の TeleMessage アカウントに毎日 1 回接続し、TeleMessage Enterprise Number Archiver を使用して従業員のモバイル通信データを Microsoft 365 のメールボックスにインポートします。

TeleMessage Enterprise Number Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Enterprise Number Archiver データに適用できます。 たとえば、コンテンツ検索を使用して TeleMessage Enterprise Number Archiver SMS、MMS、および Voice Call を検索したり、Enterprise Number Archiver コネクタ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 番号アーカイブ Enterpriseを使用してデータをインポートおよびアーカイブすると、Microsoft 365政府と規制のポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-enterprise-number-data"></a>アーカイブの概要 Enterprise数値データ

次の概要では、コネクタを使用してネットワーク データをアーカイブするプロセスEnterprise説明Microsoft 365。

![Enterprise数値アーカイブ ワークフロー。](../media/EnterpriseNumberConnectorWorkflow.png)

1. 組織は TeleMessage を使用して、番号アーカイブ Enterpriseを設定します。 詳細については、こちらを参照 [してください](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。

2. Microsoft 365 コンプライアンス センター で作成する Enterprise Number Archiver コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud の安全な Azure Storage 領域に転送します。

3. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 Number Archiver という名前Enterprise新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがそのメールボックスにインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用 *してマッピングを行* います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザー Microsoft 365対応するメールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタがカスタム マッピング ファイルまたは電子メール アイテムのユーザーの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

Enterprise Number Archiver データをアーカイブするために必要な実装手順の一部は、Microsoft 365 の外部であり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- TeleMessage から[Enterprise番号アーカイブ](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)サービスを注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 電話番号 SMS/MMS ネットワークアーカイブEnterprise必要なすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用するメール アドレスと同じMicrosoft 365してください。

- 従業員の携帯電話に TeleMessage Enterprise Number Archiver アプリをインストールしてアクティブ化します。

- Number Archiver コネクタを作成するEnterpriseには、メールボックスインポートエクスポートの役割が割り当てられている必要Exchange Online。 これは、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- このデータ コネクタは、米国政府機関GCCのMicrosoft 365環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-an-enterprise-number-archiver-connector"></a>番号アーカイブ Enterpriseを作成する

前のセクションで説明した前提条件を完了したら、Enterpriseに番号アーカイブ Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS、MMS、および音声通話メッセージを、Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. [データ コネクタ] に移動し、[数値 [https://compliance.microsoft.com](https://compliance.microsoft.com/)  \> **アーカイブEnterprise] をクリックします**。

2. [番号アーカイブ **Enterprise] ページ** で、[コネクタの追加]**をクリックします。**

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. **[TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] を **クリックします**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] を **クリックします**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [コネクタ] **タブに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。