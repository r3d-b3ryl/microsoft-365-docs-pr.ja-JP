---
title: TeleMessage Enterprise Number Archiver からデータをアーカイブするコネクタをセットアップする
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
description: 管理者は、TeleMessage Enterprise Number Archiver から SMS および MMS データをインポートおよびアーカイブするコネクタをセットアップできます。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921747"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>エンタープライズ番号データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用して、エンタープライズ 番号アーカイブからショート メッセージング サービス (SMS) メッセージ、マルチメディア メッセージング サービス (MMS) メッセージ、チャット メッセージ、音声通話録音、音声通話ログをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、組織の TeleMessage アカウントに毎日 1 回接続し、TeleMessage Enterprise Number Archiver を使用する従業員のモバイル通信データを Microsoft 365 のメールボックスにインポートします。

TeleMessage Enterprise Number Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をエンタープライズ番号アーカイバー データに適用できます。 たとえば、コンテンツ検索を使用して TeleMessage Enterprise Number Archiver SMS、MMS、および Voice Call を検索したり、エンタープライズ番号アーカイブ コネクタ データを含むメールボックスを Advanced 電子情報開示ケースの保管担当者に関連付けできます。 エンタープライズ番号アーカイブ コネクタを使用して Microsoft 365 でデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-enterprise-number-data"></a>エンタープライズ番号データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 のエンタープライズ ネットワーク データをアーカイブするプロセスについて説明します。

![エンタープライズ番号のアーカイブ ワークフロー](../media/EnterpriseNumberConnectorWorkflow.png)

1. 組織は TeleMessage と一緒にエンタープライズ番号アーカイブ コネクタをセットアップします。 詳細については、こちらを参照 [してください](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。

2. Microsoft 365 コンプライアンス センターで作成する Enterprise Number Archiver コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud の安全な Azure Storage 領域に転送します。

3. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 Enterprise Number Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用 *してマッピングを行* います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザーの対応する Microsoft 365 メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 カスタム マッピング ファイルまたは電子メール アイテムのユーザーの電子メール アドレス プロパティに有効なMicrosoft 365 ユーザーがコネクタで見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Enterprise Number Archiver データをアーカイブするために必要な実装手順の一部は、Microsoft 365 の外部であり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Enterprise Number Archiver サービスを注文し](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- TeleMessage アカウントにエンタープライズ番号 SMS/MMS ネットワーク アーカイブが必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用されているのと同じメール アドレスを使用してください。

- 従業員の携帯電話に TeleMessage Enterprise Number Archiver アプリをインストールしてアクティブ化します。

- エンタープライズ番号アーカイブ コネクタを作成するユーザーには、Exchange Online のメールボックスインポートエクスポートの役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンス センターの **[** データ コネクタ] ページにコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="create-an-enterprise-number-archiver-connector"></a>エンタープライズ番号アーカイブ コネクタの作成

前のセクションで説明した前提条件を完了したら、Microsoft 365 コンプライアンス センターに Enterprise Number Archiver コネクタを作成できます。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、SMS、MMS、音声通話メッセージを Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. [データ コネクタエンタープライズ番号アーカイブ] に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/)  \> **し、[データ コネクタ] をクリックします**。

2. [エンタープライズ番号 **アーカイブ] 製品の説明ページ** で、[コネクタの追加] **をクリックします。**

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