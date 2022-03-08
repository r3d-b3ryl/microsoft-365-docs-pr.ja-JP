---
title: T SMS/MMS ネットワーク データを使用して AT&をアーカイブするコネクタをセットアップする
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
description: 管理者は、テレメッセージ コネクタをセットアップして、SMS および MMS データを AT および T Mobile Network からインポート&アーカイブできます。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: 2b1e03c4d434b08c3dce21ed42c24e4573513c24
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322213"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>T SMS/MMS データを使用して AT&をアーカイブするコネクタをセットアップする

T Mobile Network から SMS データと MMS データMicrosoft 365 コンプライアンス センターインポートおよびアーカイブするには、このインターフェイスの TeleMessage コネクタ&使用します。 コネクタをセットアップして構成した後、組織の AT&T Network に毎日 1 回接続し、SMS および MMS データを Microsoft 365 のメールボックスにインポートします。

SMS および MMS メッセージがユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を AT&T Network データに適用できます。 たとえば、コンテンツ検索を使用して AT&T Network データを検索したり、AT&T ネットワーク コネクタ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付Advanced eDiscoveryできます。 AT&T ネットワーク コネクタを使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-att-network-data"></a>T ネットワーク データのアーカイブ AT&概要

次の概要では、コネクタを使用して、コネクタを使用して T Network データをアーカイブ&T Network データをアーカイブするMicrosoft 365。

![ATT ネットワークのアーカイブ ワークフロー。](../media/ATTNetworkConnectorWorkflow.png)

1. 組織は TeleMessage を使用して、T ネットワーク コネクタの AT&設定します。 詳細については、「 [AT&T Network Archiver」を参照してください](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)。

2. リアルタイムで、組織の AT および T ネットワークからの SMS&MMS メッセージが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センター で作成した AT&T ネットワーク コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の SMS および MMS メッセージを Microsoft クラウド内の安全な Azure Storage 場所に転送します。 また、コネクタは SMS メッセージと MMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 **T SMS/MMS ネットワーク アーカイブ&AT** という名前の新しいフォルダーがユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用して *、このマッピングを実行* します。 すべての SMS メッセージと MMS メッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。
 
   *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号Microsoft 365対応するメール アドレスが含まれている。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは電子メール アイテムの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>始める前に

AT&T Network データをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部であり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage からモバイル アーカイブ サービスを注文し](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- At&T アカウントと請求連絡先の詳細を取得して、TeleMessage オンボーディング フォームに入力し、AT&T からメッセージ アーカイブ サービスを注文できます。

- テレメッセージ アカウントで T SMS/MMS&AT を必要とするすべてのユーザーを登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用する電子メール アドレスと同じMicrosoft 365してください。

- 従業員は、AT および T モバイル ネットワークに企業所有の企業責任の携帯電話&必要があります。 ユーザーが所有Microsoft 365または "自分のデバイスを持ち込む (BYOD) デバイスでメッセージをアーカイブできません。

- T ネットワーク コネクタで AT&ユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この TeleMessage データ コネクタは、米国政府機関GCC環境Microsoft 365使用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-a-att-network-connector"></a>AT ネットワーク T&を作成する

前のセクションで説明した前提条件を完了したら、次のセクションで AT&T ネットワーク コネクタを作成Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、SMS メッセージと MMS メッセージを、メッセージ内の対応するユーザー メールボックス ボックスに転送Microsoft 365。

1. T Network に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データ コネクタ** \ **AT]&クリックします**。

2. **[AT&T Network 製品の説明] ページで**、[コネクタの追加] **をクリックします。**

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. [ **TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. コンプライアンス センターの **[データ** コネクタ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
