---
title: カスタマー キーの可用性キーの詳細
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
description: 紛失したカスタマー キーの回復に使用される可用性キーについて説明します。
ms.openlocfilehash: 1fd80d23980957402ae7d5e79a91e57d28df38f9
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761839"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>カスタマー キーの可用性キーの詳細

可用性キーは、データ暗号化ポリシーを作成するときに自動的に生成およびプロビジョニングされるルート キーです。 Microsoft 365可用性キーを格納して保護します。 可用性キーは、カスタマー キーを使用してサービスを暗号化するために指定する 2 つのルート キーと同様に機能します。 可用性キーは、キー階層内の 1 層下のキーをラップします。 Azure Key Vaultで提供および管理するキーとは異なり、可用性キーに直接アクセスすることはできません。 自動サービスMicrosoft 365、可用性キーをプログラムで管理します。 これらのサービスは、可用性キーへの直接アクセスを伴わない自動化された操作を開始します。

可用性キーの主な目的は、管理するルート キーの予期しない損失から回復機能を提供することです。 損失は、管理ミスや悪意のあるアクションの結果である可能性があります。 ルート キーの制御が失われる場合は、Microsoft サポートにお問い合わせください。Microsoft は、可用性キーを使用して復旧のプロセスを支援します。 可用性キーを使用して、プロビジョニングした新しいルート キーを使用して新しいデータ暗号化ポリシーに移行します。

可用性キーのStorageと制御は、次の 3 つの理由から Azure Key Vault キーとは意図的に異なります。

- 可用性キーは、両方の Azure Key Vault キーに対する制御が失われた場合に、復旧の "中断" 機能を提供します。
- 論理制御とセキュリティで保護されたストレージの場所を分離すると、多層防御が提供され、単一の攻撃または障害点から、すべてのキーとデータが失われから保護されます。
- 可用性キーは、一時的なエラーのためにMicrosoft 365サービスが Azure Key Vaultでホストされているキーに到達できない場合に高可用性機能を提供します。 この規則は、Exchange OnlineとSkype for Businessサービスの暗号化にのみ適用されます。 SharePoint Online、OneDrive for Business、およびTeams ファイルでは、復旧プロセスを開始するように Microsoft に明示的に指示しない限り、可用性キーは使用されません。

キー管理にさまざまな保護とプロセスを使用してデータを保護する責任を共有すると、最終的にすべてのキー (したがって、データ) が完全に失われるか破棄されるリスクが軽減されます。 Microsoft は、サービスを終了するときに可用性キーの無効化または破棄に対する唯一の権限を提供します。 設計上、Microsoft の誰も可用性キーにアクセスできないようになっています。Microsoft 365 のサービス コードからアクセスする必要があります。

キーをセキュリティで保護する方法の詳細については、 [Microsoft セキュリティ センター](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) を参照してください。
  
## <a name="availability-key-uses"></a>可用性キーで使用する

可用性キーは、外部の男性要因または悪意のあるインサイダーがキー コンテナーの制御を盗んだ場合、または不注意で管理ミスがルート キーを失う場合に、復旧機能を提供します。 この回復機能は、Customer Key と互換性のあるすべてのMicrosoft 365 サービスに適用されます。 個々のサービスでは、可用性キーの使用方法が異なります。 Microsoft 365は、以下で説明する方法でのみ可用性キーを使用します。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange OnlineとSkype for Businessが使用する

回復機能に加えて、Exchange OnlineとSkype for Businessは可用性キーを使用して、ルート キーにアクセスするサービスに関連する一時的な、または断続的な運用上の問題の間のデータ可用性を確保します。 一時的なエラーが原因でサービスが Azure Key Vaultのカスタマー キーのいずれかに到達できない場合、サービスは可用性キーを自動的に使用します。 サービスが可用性キーに直接アクセスすることはありません。

Exchange OnlineおよびSkype for Businessの自動システムでは、一時的なエラー時に可用性キーを使用して、ウイルス対策、電子検出、データ損失防止、メールボックスの移動、データ インデックス作成などの自動化されたバックエンド サービスをサポートできます。

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint Online、OneDrive for Business、およびTeams ファイルで使用されます

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは復旧機能の外部では使用されないため、お客様は復旧シナリオ中に可用性キーの使用を開始するよう Microsoft に明示的に指示する必要があります。 自動サービス操作は、Azure Key Vault 内のカスタマー キーのみに依存します。 これらのサービスのキー階層のしくみの詳細については、「[オンライン、OneDrive for Business、およびTeams ファイルで可用性キーを使用する方法](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)SharePoint参照してください。

## <a name="availability-key-security"></a>可用性キーのセキュリティ

Microsoft は、可用性キーをインスタンス化し、それを保護するための広範な措置を講じることにより、データ保護の責任をユーザーと共有します。 Microsoft は、可用性キーの直接制御を顧客に公開しません。 たとえば、Azure Key Vaultで所有しているキーのみをロール (ローテーション) できます。 詳細については、「 [顧客キーまたは可用性キーをロールまたはローテーションする](customer-key-availability-key-roll.md)」を参照してください。

### <a name="availability-key-secret-stores"></a>可用性キーシークレット ストア

Microsoft は、アクセス制御された内部シークレット ストア (顧客向けの Azure Key Vaultなど) の可用性キーを保護します。 Microsoft 管理者が内部に含まれるシークレットに直接アクセスできないように、アクセス制御を実装しています。 キーのローテーションや削除を含むシークレット ストア操作は、可用性キーへの直接アクセスを伴わない自動コマンドを使用して行われます。 シークレット ストア管理操作は特定のエンジニアに限定されており、内部ツールである Lockbox を使用した特権エスカレーションが必要です。 特権エスカレーションには、付与される前にマネージャーの承認と正当な理由が必要です。 ロックボックスを使用すると、有効期限が切れるかエンジニアがログアウトしたときにアクセスが自動的に失効し、アクセスが期限切れになります。

**Exchange OnlineとSkype for Business** の可用性キーは、Exchange Online Active Directory シークレット ストアに格納されます。 可用性キーは、Active Directory ドメイン コントローラー内のテナント固有のコンテナー内に安全に格納されます。 このセキュリティで保護されたストレージの場所は、SharePoint Online、OneDrive for Business、およびTeams ファイルシークレット ストアとは分離されています。

**SharePoint Online、OneDrive for Business、Teams ファイル** の可用性キーは、サービス チームによって管理される内部シークレット ストアに格納されます。 このセキュリティで保護されたシークレット ストレージ サービスには、アプリケーション エンドポイントとバックエンドとしてのSQL Databaseを備えたフロントエンド サーバーがあります。 可用性キーはSQL Databaseに格納され、AES-256 と HMAC の組み合わせを使用して保存時の可用性キーを暗号化するシークレット ストア暗号化キーによってラップ (暗号化) されます。 シークレット ストア暗号化キーは、同じSQL Databaseの論理的に分離されたコンポーネントに格納され、Microsoft 証明機関 (CA) によって管理される証明書に含まれる RSA-2048 キーでさらに暗号化されます。 これらの証明書は、データベースに対して操作を実行するシークレット ストア フロントエンド サーバーに格納されます。

### <a name="defense-in-depth"></a>多層防御

Microsoft は、悪意のあるアクターが Microsoft Cloud に格納されている顧客データの機密性、整合性、または可用性に影響を与えないように、多層防御戦略を採用しています。 包括的なセキュリティ戦略の一環として、シークレット ストアと可用性キーを保護するために、特定の予防および検出コントロールが実装されます。

Microsoft 365は、可用性キーの誤用を防ぐために構築されています。 アプリケーション層は、可用性キーを含むキーを使用してデータの暗号化と暗号化解除を行うことができる唯一の方法です。 サービス コードMicrosoft 365にのみ、暗号化と復号化アクティビティのキー階層を解釈して走査する機能があります。 カスタマー キー、可用性キー、その他の階層キー、および顧客データの格納場所の間には、論理的な分離が存在します。 この分離により、1 つ以上の場所が侵害された場合のデータ漏洩のリスクが軽減されます。 階層内の各レイヤーには、格納されたデータとシークレットを保護するための 24 時間 365 日の侵入検出機能が組み込まれています。

アクセス制御は、可用性キー シークレット ストアを含む内部システムへの不正アクセスを防ぐために実装されます。 Microsoft エンジニアは、可用性キー シークレット ストアに直接アクセスできません。 アクセス制御の詳細については、[Microsoft 365の管理アクセス制御に](/compliance/assurance/assurance-administrative-access-controls-overview)関するページを参照してください。

技術的な制御により、Microsoft の担当者は高い特権を持つサービス アカウントにログインできなくなります。それ以外の場合は、攻撃者がMicrosoft サービスを偽装するために使用される可能性があります。 たとえば、これらのコントロールは対話型ログオンを防止します。

セキュリティ ログと監視の制御は、Microsoft サービスとデータに対するリスクを軽減する多層防御のもう 1 つの保護手段です。 Microsoft サービス チームは、アラートと監査ログを生成するアクティブな監視ソリューションをデプロイしました。 すべてのサービス チームは、ログを集約して処理する中央リポジトリにログをアップロードします。 内部ツールは、レコードを自動的に調べて、サービスが最適で回復性があり、セキュリティで保護された状態で機能していることを確認します。 通常とは異なるアクティビティには、さらなるレビューのフラグが設定されます。

Microsoft セキュリティ ポリシー違反の可能性を示すログ イベントは、直ちに Microsoft セキュリティ チームの注意を引きます。 Microsoft 365セキュリティは、可用性キー シークレット ストアへのアクセス試行を検出するようにアラートを構成しました。 また、Microsoft の担当者がサービス アカウントへの対話型ログオンを試みる場合にもアラートが生成されます。これは、アクセス制御によって禁止および保護されています。 Microsoft 365セキュリティでは、通常のベースライン操作からMicrosoft 365 サービスが逸脱した場合にも、検出とアラートが行われます。 Microsoft 365 サービスを悪用しようとする男性要因は、アラートをトリガーし、その結果、Microsoft クラウド環境から違反者が立ち退くことになります。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>可用性キーを使用してキーの損失から回復する

カスタマー キーの制御を失った場合、可用性キーを使用すると、データを回復して再暗号化できます。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange OnlineとSkype for Businessの復旧手順

カスタマー キーの制御を失った場合、可用性キーを使用すると、データを回復し、影響を受けるMicrosoft 365 リソースをオンラインに戻す機能が提供されます。 可用性キーは、復旧中も引き続きデータを保護します。高いレベルでは、キーの損失から完全に回復するには、新しい DEP を作成し、影響を受けるリソースを新しいポリシーに移動する必要があります。

新しいカスタマー キーを使用してデータを暗号化するには、Azure Key Vaultに新しいキーを作成し、新しいカスタマー キーを使用して新しい DEP を作成し、キーが紛失または侵害された前の DEP で現在暗号化されているメールボックスに新しい DEP を割り当てます。

この再暗号化プロセスには、最大 72 時間かかる場合があります。 これは、DEP を変更するときの標準的な期間です。
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルの復旧手順

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは復旧機能の外部では使用されません。 復旧シナリオ中に可用性キーの使用を開始するように Microsoft に明示的に指示する必要があります。 回復プロセスを開始するには、Microsoft に連絡して可用性キーをアクティブ化します。 アクティブ化されると、可用性キーが自動的に使用されてデータの暗号化が解除され、新しく作成された DEP を新しい顧客キーに関連付けてデータを暗号化できます。  

この操作は、組織内のサイトの数に比例します。 Microsoft に電話して可用性キーを使用したら、約 4 時間以内に完全にオンラインになります。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>可用性キーのExchange OnlineとSkype for Businessの使用方法

Customer Key を使用して DEP を作成すると、Microsoft 365その DEP に関連付けられたデータ暗号化ポリシー キー (DEP キー) が生成されます。 サービスは DEP キーを 3 回暗号化します。1 回は顧客の各キーで、1 回は可用性キーを使用します。 DEP キーの暗号化されたバージョンのみが格納され、DEP キーはカスタマー キーまたは可用性キーでのみ復号化できます。 DEP キーは、個々のメールボックスを暗号化するメールボックス キーを暗号化するために使用されます。
  
Microsoft 365は、このプロセスに従って、顧客がサービスを使用しているときにデータを復号化して提供します。
  
1. カスタマー キーを使用して DEP キーを復号化します。

2. 復号化された DEP キーを使用して、メールボックス キーを復号化します。

3. 復号化されたメールボックス キーを使用してメールボックス自体を復号化し、メールボックス内のデータにアクセスできるようにします。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>オンライン ファイル、OneDrive for Business ファイル、Teams ファイルSharePoint可用性キーの使用方法

カスタマー キーと可用性キーのSharePoint Online およびOneDrive for Businessアーキテクチャと実装は、Exchange OnlineとSkype for Businessとは異なります。
  
組織がカスタマー マネージド キーに移行すると、Microsoft 365組織固有の中間キー (TIK) が作成されます。 Microsoft 365は TIK を 2 回暗号化し、各顧客キーを使用して 1 回ずつ暗号化し、2 つの暗号化されたバージョンの TIK を格納します。 TIK の暗号化されたバージョンのみが格納され、TIK はカスタマー キーでのみ復号化できます。 その後、TIK はサイト キーの暗号化に使用され、BLOB キー (ファイル チャンク キーとも呼ばれます) の暗号化に使用されます。 ファイル サイズによっては、サービスによって、一意のキーを持つ複数のファイル チャンクにファイルが分割される場合があります。 BLOB (ファイル チャンク) 自体は、BLOB キーで暗号化され、Microsoft Azure Blob Storage サービスに格納されます。
  
Microsoft 365は、このプロセスに従って、顧客がサービスを使用しているときに顧客ファイルを暗号化解除して提供します。

1. カスタマー キーを使用して TIK を復号化します。

2. 復号化された TIK を使用してサイト キーを復号化します。

3. 暗号化解除されたサイト キーを使用して BLOB キーを復号化します。

4. 暗号化解除された BLOB キーを使用して BLOB の暗号化を解除します。

Microsoft 365は、わずかなオフセットで Azure Key Vaultに 2 つの復号化要求を発行することで、TIK の暗号化を解除します。 最初に完了すると、結果が提供され、もう一方の要求が取り消されます。
  
顧客キーにアクセスできなくなった場合、Microsoft 365は可用性キーを使用して TIK を暗号化し、これを各顧客キーで暗号化された TIK と共に格納します。 可用性キーで暗号化された TIK は、お客様が Microsoft に電話して、悪意を持って、または誤ってキーにアクセスできなくなった場合にのみ使用されます。
  
可用性とスケールの理由から、復号化された TIK は時間制限付きメモリ キャッシュにキャッシュされます。 TIK キャッシュの有効期限が切れる 2 時間前Microsoft 365、各 TIK の暗号化解除が試行されます。 TIK を復号化すると、キャッシュの有効期間が延長されます。 TIK 復号化に長時間失敗した場合、Microsoft 365キャッシュの有効期限が切れる前にエンジニアリングに通知するアラートが生成されます。 お客様が Microsoft を呼び出す場合にのみ、復旧操作が開始Microsoft 365。これには、Microsoft のシークレット ストアに格納されている可用性キーを使用して TIK の暗号化を解除し、暗号化解除された TIK と顧客が提供する新しい Azure Key Vault キーのセットを使用してテナントを再びオンボードする必要があります。
  
現在、カスタマー キーは、Azure BLOB ストアに格納されている SharePoint Online ファイル データの暗号化と暗号化解除チェーンに関与していますが、SQL Databaseに格納されているオンライン リスト アイテムやメタデータSharePointされません。 Microsoft 365は、上記のケース以外のExchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルには可用性キーを使用しません。顧客によって開始されます。 顧客データへのヒューマン アクセスは、Customer Lockbox によって保護されます。

## <a name="availability-key-triggers"></a>可用性キートリガー

Microsoft 365特定の状況でのみ可用性キーをトリガーします。 これらの状況はサービスによって異なります。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange OnlineとSkype for Businessのトリガー
  
1. Microsoft 365は、メールボックスが割り当てられている DEP を読み取って、Azure Key Vaultの 2 つのカスタマー キーの場所を決定します。

2. Microsoft 365 DEP から 2 つのカスタマー キーのいずれかをランダムに選択し、顧客キーを使用して DEP キーをラップ解除する要求を Azure Key Vaultに送信します。

3. カスタマー キーを使用して DEP キーをラップ解除する要求が失敗した場合、Microsoft 365は Azure Key Vaultに 2 番目の要求を送信します。この場合は、代替の (2 番目の) カスタマー キーを使用するように指示します。

4. カスタマー キーを使用して DEP キーをラップ解除する 2 番目の要求が失敗した場合、Microsoft 365は両方の要求の結果を調べます。

    - 要求が失敗してシステム エラーが返されたと判定された場合は、次のようになります。

       - Microsoft 365は、DEP キーを復号化するために可用性キーをトリガーします。

       - その後、Microsoft 365 DEP キーを使用してメールボックス キーを復号化し、ユーザー要求を完了します。 

       - この場合、Azure Key Vaultは応答できないか、一時的なエラーが原因で到達できません。

    - 要求が ACCESS DENIED の返しに失敗したと判定された場合は、次のようになります。

       - これは、顧客キーを使用できないようにするために意図的、不注意、または悪意のあるアクションが実行されたことを意味します (たとえば、サービスを離れる一環としてデータ消去プロセス中)。

       - この場合、可用性キーはシステム アクションにのみ使用され、ユーザー アクションには使用されず、ユーザー要求は失敗し、ユーザーはエラー メッセージを受信します。

> [!IMPORTANT]
> Microsoft 365サービス コードには、付加価値の高いクラウド サービスを提供するために顧客データを推論するための有効なログイン トークンが常に用意されています。 したがって、可用性キーが削除されるまでは、検索インデックスの作成やメールボックスの移動など、Exchange OnlineおよびSkype for Businessによって開始されるアクションまたは内部操作のフォールバックとして使用できます。 これは、Azure Key Vaultに対する一時的なエラーと ACCESS DENIED 要求の両方に適用されます。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのトリガー

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは復旧機能の外部では使用されないため、お客様は復旧シナリオ中に可用性キーの使用を開始するよう Microsoft に明示的に指示する必要があります。

## <a name="audit-logs-and-the-availability-key"></a>監査ログと可用性キー

Microsoft 365の自動化されたシステムは、システムを通過する際にすべてのデータを処理して、ウイルス対策、電子検出、データ損失防止、データ インデックス作成などのクラウド サービスを提供します。 Microsoft 365では、このアクティビティの顧客が表示できるログは生成されません。 さらに、Microsoft 担当者は、これらの通常のシステム操作の一部としてデータにアクセスしません。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>可用性キーのログ記録のExchange OnlineとSkype for Business

Exchange OnlineとSkype for Businessが可用性キーにアクセスしてサービスを提供すると、セキュリティとコンプライアンス センターからアクセスできる顧客が見えるログが発行Microsoft 365。 可用性キー操作の監査ログ レコードは、サービスが可用性キーを使用するたびに生成されます。 アクティビティの種類が "可用性キーへのフォールバック" の "Customer Key Service Encryption" という新しいレコードの種類を使用すると、管理者 [は統合監査ログ](./search-the-audit-log-in-security-and-compliance.md) の検索結果をフィルター処理して可用性キー レコードを表示できます。

ログ レコードには、日付、時刻、アクティビティ、組織 ID、データ暗号化ポリシー ID などの属性が含まれます。 このレコードは統合監査ログの一部として使用でき、[セキュリティ & コンプライアンス センター監査ログ検索] タブからアクセスできます。

![可用性キー イベントの監査ログ検索](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

可用性キー レコードExchange OnlineおよびSkype for Businessでは、カスタム パラメーター (ポリシー ID、スコープ キー バージョン ID、要求 ID) を追加して、Office 365管理アクティビティ[共通スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)を使用します。

![可用性キーのカスタム パラメーター](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーのログ記録

これらのサービスでは、可用性キーのログ記録はまだ利用できません。 SharePoint Online、OneDrive for Business、およびTeams ファイルの場合、可用性キーは、回復のために Microsoft から指示を受けた場合にのみアクティブ化されます。 その結果、これらのサービスに可用性キーが使用されるすべてのイベントが既にわかっています。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>カスタマー キー階層の可用性キー
  
Microsoft 365は、可用性キーを使用して、Customer Key Service 暗号化用に確立されたキー階層の下位にあるキーの層をラップします。 サービス間には、異なるキー階層が存在します。 キー アルゴリズムは、可用性キーと、該当する各サービスの階層内の他のキーでも異なります。 さまざまなサービスで使用される可用性キー アルゴリズムは次のとおりです。

- Exchange OnlineキーとSkype for Business可用性キーでは、AES-256 が使用されます。

- SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーでは、RSA-2048 が使用されます。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange OnlineとSkype for Businessのキーを暗号化するために使用される暗号化暗号

![Exchange Onlineカスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online およびOneDrive for Businessのキーを暗号化するために使用される暗号化暗号

![SharePoint Online カスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [カスタマー キーを設定する](customer-key-set-up.md)

- [カスタマー キーを管理する](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)
