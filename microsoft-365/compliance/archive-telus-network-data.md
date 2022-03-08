---
title: コネクタをセットアップして、TELUS Network データをアーカイブMicrosoft 365
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
description: 管理者は、テレメッセージ コネクタをセットアップして、電話会社の TELUS ネットワークから SMS データをインポートおよびアーカイブMicrosoft 365。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: 7aca24c39f9eba5dba532f1224ad68d5ff1d4568
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327393"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a>TELUS ネットワーク データをアーカイブするコネクタをセットアップする

組織の TELUS ネットワークからショート メッセージング Microsoft 365 コンプライアンス センター (SMS) データをインポートおよびアーカイブするには、次のサイトの TeleMessage コネクタを使用します。 コネクタをセットアップして構成した後、毎日 1 回、組織の TELUS ネットワークに接続し、SMS データを Microsoft 365 のメールボックスにインポートします。

SMS メッセージをユーザー メールボックスに保存した後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどのコンプライアンス機能を TELUS データに適用Microsoft 365できます。 たとえば、コンテンツ検索を使用して TELUS SMS メッセージを検索したり、TELUS データを含むメールボックスを管理担当者に関連付Advanced eDiscoveryできます。 TELUS ネットワーク コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-telus-network-data"></a>TELUS ネットワーク データのアーカイブの概要

次の概要では、コネクタを使用して TELUS Network データをアーカイブするプロセスについて説明Microsoft 365。

![TELUS Network アーカイブ ワークフロー。](../media/TelusNetworkConnectorWorkflow.png)

1. 組織は、TeleMessage と TELUS を使用して TELUS ネットワーク コネクタをセットアップします。 詳細については、「 [TELUS Network Archiver」を参照してください](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)。

2. リアルタイムで、組織の TELUS ネットワークからの SMS メッセージが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センター で作成した TELUS ネットワーク コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の SMS メッセージを Microsoft クラウド内の安全な Azure Storage 場所に転送します。 また、コネクタは SMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 **TELUS SMS Network Archiver** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用 *してマッピングを行* います。 すべての SMS メッセージには、このプロパティが含まれるので、SMS メッセージのすべての参加者の電子メール アドレスが設定されます。

   *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号Microsoft 365対応するメール アドレスが含まれている。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての TELUS アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは TELUS アイテムの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

TELUS Network データのアーカイブに必要な実装手順の一部は、Microsoft 365 の外部であり、コンプライアンス センターにコネクタを作成する前に完了する必要があります。

- [TeleMessage から TELUS Network Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- TELUS ネットワーク アカウントと請求連絡先の詳細を取得して、TeleMessage オンボーディング フォームに入力し、TELUS からメッセージ アーカイブ サービスを注文できます。

- TELUS SMS ネットワークのアーカイブを必要とするすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用する電子メール アドレスと同じMicrosoft 365してください。

- 従業員がTELUS モバイル ネットワーク上に企業所有および企業責任を持つ携帯電話を持っている必要があります。 ユーザーが所有Microsoft 365デバイスまたは自分のデバイスを持ち込む (BYOD) デバイスでは、アーカイブ メッセージを使用できません。

- TELUS ネットワーク コネクタを作成するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この TeleMessage データ コネクタは、米国政府機関GCC環境Microsoft 365使用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-a-telus-network-connector"></a>TELUS ネットワーク コネクタの作成

前のセクションで説明した前提条件を完了したら、このセクションで TELUS Network コネクタを作成Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、SMS メッセージを、メッセージ内の対応するユーザー メールボックス ボックスに転送Microsoft 365。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/)]TELUS **ネットワークに** > 移動 **し、[データ コネクタ] をクリックします**。

2. **[TELUS ネットワーク製品の説明]** ページで、[コネクタの追加] **をクリックします。**

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. [ **TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にして、[次へ] を **クリックします**。 カスタム マッピングが必要な場合は、CSV ファイルをアップロードし、[次へ] を **クリックします**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [ **コネクタ] タブに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
