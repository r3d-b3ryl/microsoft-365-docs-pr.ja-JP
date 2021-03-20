---
title: カスタマー キーの可用性キーの詳細
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 紛失した顧客キーの回復に使用される可用性キーについて学習します。
ms.openlocfilehash: bbad6ace0880c142a497bcac3469c579f13c7881
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907743"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>カスタマー キーの可用性キーの詳細

可用性キーは、データ暗号化ポリシーを作成するときに自動的に生成およびプロビジョニングされるルート キーです。 Microsoft 365 は可用性キーを保存および保護します。 可用性キーは、カスタマー キーを使用してサービスの暗号化を行う 2 つのルート キーと機能的に似た機能を持つ。 可用性キーは、キー階層の下位 1 層のキーをラップします。 Azure Key Vault で提供および管理するキーとは異なり、可用性キーに直接アクセスすることはできません。 Microsoft 365 の自動サービスは、可用性キーをプログラムで管理します。 これらのサービスは、可用性キーへの直接アクセスを伴う自動操作を開始します。

可用性キーの主な目的は、管理するルート キーの不当な損失からの回復機能を提供します。 損失は、不正な処理や悪意のあるアクションの結果である可能性があります。 ルート キーの制御が失われる場合は、Microsoft サポートに問い合わせ、可用性キーを使用した回復プロセスを支援します。 可用性キーを使用して、プロビジョニングする新しいルート キーを使用して新しいデータ暗号化ポリシーに移行します。

可用性キーの記憶域と制御は、3 つの理由で Azure Key Vault キーとは意図的に異なります。

- 可用性キーは、両方の Azure Key Vault キーの制御が失われた場合に、回復機能 "break-glass" 機能を提供します。
- 論理コントロールとセキュリティで保護された記憶域の場所を分離すると、詳細な防御が提供され、1 回の攻撃または障害点からすべてのキーとデータが失われるのを防います。
- 可用性キーは、Microsoft 365 サービスが一時的なエラーのために Azure Key Vault でホストされているキーに到達できない場合に、高可用性機能を提供します。 このルールは、Exchange Online および Skype for Business サービス暗号化にのみ適用されます。 SharePoint Online、OneDrive for Business、Teams ファイルは、回復プロセスを開始するように明示的に Microsoft に指示しない限り、可用性キーを使用しない。

キー管理にさまざまな保護とプロセスを使用して、データを保護する責任を共有することで、最終的に、すべてのキー (したがってデータ) が完全に失われたり破棄されるリスクが軽減されます。 Microsoft は、サービスを離れる際に可用性キーの無効化または破棄に関する唯一の権限を提供します。 設計上、Microsoft の誰も可用性キーにアクセスできないようになっています。Microsoft 365 のサービス コードからアクセスする必要があります。

キーを [セキュリティで保護する方法の詳細については、「Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) Trust Center」を参照してください。
  
## <a name="availability-key-uses"></a>可用性キーの使用

可用性キーは、外部の男性要素または悪意のあるインサイダーがキー コンテナーの制御を盗むシナリオ、または誤った管理によってルート キーが失われるシナリオの回復機能を提供します。 この回復機能は、顧客キーと互換性のあるすべての Microsoft 365 サービスに適用されます。 個々のサービスでは、可用性キーの使い方が異なります。 Microsoft 365 では、以下で説明する方法でのみ可用性キーを使用します。

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online と Skype for Business の使用

回復機能に加えて、Exchange Online と Skype for Business は可用性キーを使用して、ルート キーにアクセスするサービスに関連する一時的な、または断続的な運用上の問題の間にデータが利用可能な状態を確保します。 一時的なエラーにより、サービスが Azure Key Vault のカスタマー キーに到達できない場合、サービスは可用性キーを自動的に使用します。 サービスは可用性キーに直接行く必要があります。

Exchange Online および Skype for Business の自動化されたシステムは、一時的なエラー時に可用性キーを使用して、ウイルス対策、電子検出、データ損失防止、メールボックスの移動、データ インデックス作成などの自動化されたバック エンド サービスをサポートすることがあります。

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint Online、OneDrive for Business、Teams ファイルの使用

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは回復機能の外部では使用されません。回復シナリオ中に可用性キーの使用を開始するように明示的に Microsoft に指示する必要があります。 自動サービス操作は、Azure Key Vault のカスタマー キーのみに依存します。 これらのサービスのキー階層のしくみの詳細については [、「SharePoint Online、OneDrive for Business、Teams](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)ファイルが可用性キーを使用する方法」を参照してください。

## <a name="availability-key-security"></a>可用性キーのセキュリティ

Microsoft は、可用性キーをインスタンス化し、それを保護するための広範な措置を講じ、データ保護の責任をユーザーと共有します。 Microsoft は、可用性キーの直接制御を顧客に公開しない。 たとえば、Azure Key Vault で所有しているキーのみをロール (回転) できます。 詳細については、「顧客キーまたは可用性 [キーのロールまたはローテーション」を参照してください](customer-key-availability-key-roll.md)。

### <a name="availability-key-secret-stores"></a>可用性キーシークレット ストア

Microsoft は、アクセス制御された内部シークレット ストア (顧客向け Azure Key Vault など) の可用性キーを保護します。 Microsoft 管理者が内に含まれるシークレットに直接アクセスするのを防ぐため、アクセス制御を実装しています。 キーのローテーションや削除を含むシークレット ストア操作は、可用性キーへの直接アクセスを必要としない自動コマンドを使用して実行されます。 シークレット ストア管理操作は特定のエンジニアに限定され、内部ツール Lockbox を介して特権エスカレーションが必要です。 特権のエスカレーションには、付与される前に管理者の承認と正当化が必要です。 Lockbox は、時間の有効期限が切れ、またはエンジニアがログアウトすると、アクセスが自動アクセス失効によって時間にバインドされます。

**Exchange Online および Skype for Business** 可用性キーは、Exchange Online Active Directory シークレット ストアに格納されます。 可用性キーは、Active Directory ドメイン コントローラー内のテナント固有のコンテナー内に安全に格納されます。 このセキュリティで保護された記憶域の場所は、SharePoint Online、OneDrive for Business、Teams ファイル シークレット ストアとは分離されています。

**SharePoint Online、OneDrive for Business、Teams** ファイルの可用性キーは、サービス チームが管理する内部シークレット ストアに格納されます。 このセキュリティで保護されたシークレット ストレージ サービスには、アプリケーション エンドポイントを備え、SQLデータベースをバック エンドとして持つフロントエンド サーバーがあります。 可用性キーは SQL データベースに格納され、AES-256 と HMAC の組み合わせを使用して保存時の可用性キーを暗号化するシークレット ストア暗号化キーによってラップ (暗号化) されます。 シークレット ストアの暗号化キーは、同じ SQL データベースの論理的に分離されたコンポーネントに格納され、Microsoft 証明機関 (CA) によって管理される証明書に含まれる RSA-2048 キーでさらに暗号化されます。 これらの証明書は、データベースに対して操作を実行するシークレット ストア フロントエンド サーバーに格納されます。

### <a name="defense-in-depth"></a>詳細な防御

Microsoft は、悪意のあるアクターが Microsoft Cloud に保存されている顧客データの機密性、整合性、または可用性に影響を与えるのを防ぐため、詳細な防御戦略を採用しています。 包括的なセキュリティ戦略の一環として、シークレット ストアと可用性キーを保護するために、特定の予防および検出コントロールが実装されています。

Microsoft 365 は、可用性キーの誤用を防ぐために構築されています。 アプリケーション層は、可用性キーを含むキーを使用してデータの暗号化と解読を行う唯一の方法です。 Microsoft 365 サービス コードだけが、暗号化と復号化のアクティビティのためにキー階層を解釈および走査できます。 論理的な分離は、顧客キー、可用性キー、その他の階層キー、および顧客データの保存場所の間に存在します。 この分離により、1 つ以上の場所が侵害された場合にデータが漏洩するリスクが軽減されます。 階層内の各レイヤーには、格納されているデータとシークレットを保護するために 24 時間 365 日の侵入検出機能が組み込まれています。

アクセス制御は、可用性キー シークレット ストアを含む内部システムへの不正アクセスを防止するために実装されています。 Microsoft のエンジニアは、可用性キー シークレット ストアに直接アクセスできます。 アクセス制御の詳細については [、「Microsoft 365 の管理アクセス制御」を参照してください](/Office365/securitycompliance/office-365-administrative-access-controls-overview)。

技術的な制御により、Microsoft の担当者は高い特権を持つサービス アカウントにログインすることを防止します。それ以外の場合は、攻撃者が Microsoft サービスを偽装するために使用される可能性があります。 たとえば、これらのコントロールは対話型ログオンを防止します。

セキュリティ ログおよび監視制御は、Microsoft サービスとデータに対するリスクを軽減する、もう 1 つの詳細な防御手段です。 Microsoft サービス チームは、アラートと監査ログを生成するアクティブな監視ソリューションを展開しました。 すべてのサービス チームは、ログを集約して処理する中央リポジトリにログをアップロードします。 内部ツールはレコードを自動的に調べて、サービスが最適で回復力があり、安全な状態で機能しているのを確認します。 異常なアクティビティには、さらに確認のフラグが設定されています。

Microsoft セキュリティ ポリシーに違反する可能性を示すログ イベントは、直ちに Microsoft セキュリティ チームの注目を集めています。 Microsoft 365 セキュリティは、可用性キー シークレット ストアへのアクセス試行を検出するようにアラートを構成しました。 また、Microsoft の担当者がサービス アカウントへの対話型ログオンを試みる場合もアラートが生成されます。これは、アクセス制御によって禁止および保護されています。 また、Microsoft 365 セキュリティは、Microsoft 365 サービスが通常のベースライン操作から逸脱した場合にも検出および通知を行います。 Microsoft 365 サービスの誤用を試みる Malefactors は、アラートをトリガーし、その結果、Microsoft クラウド環境から犯罪者が立ち退く可能性があります。

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>可用性キーを使用してキー損失から回復する

顧客キーの制御を失った場合、可用性キーを使用すると、データを回復して再暗号化できます。

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business の回復手順

顧客キーの制御を失った場合、可用性キーを使用すると、データを回復し、影響を受ける Microsoft 365 リソースをオンラインに戻す機能が提供されます。 可用性キーは、回復中も引き続きデータを保護します。大きなレベルでは、キー損失から完全に回復するには、新しい DEP を作成し、影響を受け取ったリソースを新しいポリシーに移動する必要があります。

新しい顧客キーを使用してデータを暗号化するには、Azure Key Vault で新しいキーを作成し、新しい顧客キーを使用して新しい DEP を作成し、キーが失われたり侵害された以前の DEP で現在暗号化されているメールボックスに新しい DEP を割り当てる必要があります。

この再暗号化プロセスには最大 72 時間かかる場合があります。 これは、DEP を変更する場合の標準の期間です。
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルの回復手順

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは回復機能以外では使用されません。 回復シナリオ中に可用性キーの使用を開始するように Microsoft に明示的に指示する必要があります。 回復プロセスを開始するには、Microsoft に問い合わせ、可用性キーをアクティブ化します。 アクティブ化されると、可用性キーが自動的に使用され、新しい顧客キーに関連付けられた新しく作成された DEP を使用してデータを暗号化できます。  

この操作は、組織内のサイトの数に比例します。 可用性キーを使用するために Microsoft に電話すると、約 4 時間以内に完全にオンラインになる必要があります。

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Exchange Online と Skype for Business が可用性キーを使用する方法

顧客キーを使用して DEP を作成すると、Microsoft 365 は、その DEP に関連付けられたデータ暗号化ポリシー キー (DEP キー) を生成します。 このサービスは、DEP キーを 3 回暗号化します。各顧客キーで 1 回、可用性キーを使用して 1 回暗号化します。 暗号化されたバージョンの DEP キーだけが格納され、DEP キーは顧客キーまたは可用性キーでのみ復号化できます。 次に、DEP キーを使用してメールボックス キーを暗号化し、個々のメールボックスを暗号化します。
  
Microsoft 365 は、次のプロセスに従って、顧客がサービスを使用している場合にデータを復号化して提供します。
  
1. 顧客キーを使用して DEP キーを復号化します。

2. 復号化された DEP キーを使用してメールボックス キーを復号化します。

3. 復号化されたメールボックス キーを使用してメールボックス自体を復号化し、メールボックス内のデータにアクセスできます。

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>SharePoint Online、OneDrive for Business、Teams ファイルが可用性キーを使用する方法

SharePoint Online および OneDrive for Business アーキテクチャとカスタマー キーと可用性キーの実装は、Exchange Online および Skype for Business とは異なります。
  
組織が顧客管理キーに移動すると、Microsoft 365 は組織固有の中間キー (TIK) を作成します。 Microsoft 365 は TIK を 2 回、顧客キーごとに 1 回暗号化し、TIK の 2 つの暗号化されたバージョンを格納します。 暗号化されたバージョンの TIK だけが格納され、TIK は顧客キーでのみ暗号化解除できます。 次に、TIK を使用してサイト キーを暗号化し、BLOB キー (ファイル チャンク キーとも呼ばれる) を暗号化するために使用されます。 ファイル サイズに応じて、サービスはファイルを一意のキーで複数のファイル チャンクに分割する場合があります。 BLOB (ファイル チャンク) 自体は BLOB キーで暗号化され、Microsoft Azure Blob ストレージ サービスに格納されます。
  
Microsoft 365 は、次のプロセスに従って、顧客がサービスを使用している場合に顧客ファイルを復号化して提供します。

1. 顧客キーを使用して TIK を復号化します。

2. 復号化された TIK を使用してサイト キーを復号化します。

3. 暗号化解除されたサイト キーを使用して、BLOB キーを復号化します。

4. 復号化された BLOB キーを使用して、BLOB を復号化します。

Microsoft 365 は、わずかなオフセットで Azure Key Vault に 2 つの復号化要求を発行して TIK を復号化します。 最初に終了すると、結果が表示されます。もう一方の要求はキャンセルされます。
  
顧客キーへのアクセスが失われる場合、Microsoft 365 は可用性キーを使用して TIK を暗号化し、これを各顧客キーで暗号化された TIK と共に保存します。 可用性キーで暗号化された TIK は、悪意のある、または誤ってキーへのアクセスを失った場合に、回復パスを登録するために Microsoft に電話した場合にのみ使用されます。
  
可用性とスケール上の理由から、復号化された TIK は時間制限付きメモリ キャッシュにキャッシュされます。 TIK キャッシュの有効期限が切れる 2 時間前に、Microsoft 365 は各 TIK の暗号化解除を試みます。 TIK を復号化すると、キャッシュの有効期間が延長されます。 TIK 復号化が大幅に失敗した場合、Microsoft 365 は、キャッシュの有効期限の前にエンジニアリングに通知するアラートを生成します。 Microsoft が Microsoft 365 を呼び出した場合にのみ、回復操作が開始されます。この操作では、Microsoft のシークレット ストアに保存されている可用性キーを使用して TIK を復号化し、復号化された TIK キーと顧客が提供する Azure Key Vault キーの新しいセットを使用してテナントを再びオンボーディングします。
  
現在、カスタマー キーは、Azure BLOB ストアに格納されている SharePoint Online ファイル データの暗号化と復号化チェーンに関与していますが、SQL データベースに格納されている SharePoint Online リスト アイテムやメタデータには関係しません。 Microsoft 365 では、上記のケース以外の Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーは使用されません。これはお客様が開始します。 顧客データへの人間のアクセスは、Customer Lockbox によって保護されます。

## <a name="availability-key-triggers"></a>可用性キートリガー

Microsoft 365 は、特定の状況でのみ可用性キーをトリガーします。 これらの状況はサービスによって異なります。

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のトリガー
  
1. Microsoft 365 は、メールボックスが割り当てられている DEP を読み取り、Azure Key Vault の 2 つの顧客キーの場所を特定します。

2. Microsoft 365 は、DEP から 2 つの顧客キーの 1 つをランダムに選択し、顧客キーを使用して DEP キーのラップを解除する要求を Azure Key Vault に送信します。

3. 顧客キーを使用して DEP キーをラップ解除する要求が失敗した場合、Microsoft 365 は 2 番目の要求を Azure Key Vault に送信します。この場合は、代替 (2 番目) の顧客キーを使用するように指示します。

4. 顧客キーを使用して DEP キーをアンラップする 2 番目の要求が失敗した場合、Microsoft 365 は両方の要求の結果を調べる。

    - システムエラーを返す要求が失敗したと判断された場合は、次の処理を行います。

       - Microsoft 365 は、DEP キーを復号化するために可用性キーをトリガーします。

       - その後、Microsoft 365 は DEP キーを使用してメールボックス キーを復号化し、ユーザー要求を完了します。 

       - この場合、一時的なエラーが原因で Azure Key Vault が応答できないか、到達不能になります。

    - 要求が ACCESS DENIED の戻り値に失敗したと判断した場合は、次の処理を行います。

       - つまり、意図的、不注意、または悪意のあるアクションが実行され、顧客キーが使用不能になります (たとえば、サービスを離れる一部としてデータの削除プロセス中)。

       - この場合、可用性キーはシステムアクションにのみ使用され、ユーザーアクションには使用されません。ユーザー要求は失敗し、ユーザーはエラー メッセージを受け取ります。

>[!IMPORTANT]
>Microsoft 365 サービス コードには、価値を追加するクラウド サービスを提供するために顧客データを理由にした有効なログイン トークンが常に含まれます。 したがって、可用性キーが削除されるまでは、Exchange Online および Skype for Business (検索インデックスの作成やメールボックスの移動など) によって開始または内部で開始されるアクションのフォールバックとして使用できます。 これは、Azure Key Vault に対する一時的な ERRORS 要求と ACCESS DENIED 要求の両方に適用されます。

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのトリガー

SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは回復機能の外部では使用されません。回復シナリオ中に可用性キーの使用を開始するように明示的に Microsoft に指示する必要があります。

## <a name="audit-logs-and-the-availability-key"></a>監査ログと可用性キー

Microsoft 365 の自動システムは、システムを流れるすべてのデータを処理して、ウイルス対策、電子検出、データ損失防止、データ インデックス作成などのクラウド サービスを提供します。 Microsoft 365 では、このアクティビティの顧客に表示されるログは生成されません。 さらに、Microsoft の担当者は、これらの通常のシステム操作の一部としてデータにアクセスしない。

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online と Skype for Business 可用性キーログ

Exchange Online と Skype for Business が可用性キーにアクセスしてサービスを提供すると、Microsoft 365 はセキュリティとコンプライアンス センターからアクセスできる顧客に表示されるログを発行します。 可用性キー操作の監査ログ レコードは、サービスが可用性キーを使用する度に生成されます。 アクティビティの種類が "フォールバック to 可用性キー" の "Customer Key Service Encryption"[](./search-the-audit-log-in-security-and-compliance.md)と呼ばれる新しいレコードの種類を使用すると、管理者は統合監査ログ検索結果をフィルター処理して可用性キー レコードを表示できます。

ログ レコードには、日付、時刻、アクティビティ、組織 ID、データ暗号化ポリシー ID などの属性が含まれます。 このレコードは統合監査ログの一部として使用できます。[コンプライアンス センター監査ログの検索] タブの [セキュリティ &からアクセスできます。

![可用性キー イベントの監査ログ検索](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online および Skype for Business 可用性キー レコードは、Office 365 管理アクティビティ共通スキーマを使用し、カスタム パラメーター (ポリシー ID、スコープ キーバージョン ID、要求 ID) を追加します。 [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

![可用性キーのカスタム パラメーター](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーログ

可用性キーのログは、これらのサービスでまだ利用できません。 SharePoint Online、OneDrive for Business、Teams ファイルの場合、可用性キーは、回復の目的で Microsoft から指示された場合にのみアクティブ化されます。 その結果、これらのサービスで可用性キーが使用されるすべてのイベントが既にわかっています。

## <a name="availability-key-in-the-customer-key-hierarchy"></a>顧客キー階層の可用性キー
  
Microsoft 365 では、可用性キーを使用して、顧客キー サービスの暗号化用に確立されたキー階層の下位のキー層をラップします。 サービス間には異なるキー階層が存在します。 また、キー アルゴリズムは、利用可能なキーと、該当する各サービスの階層内の他のキーによっても異なります。 さまざまなサービスで使用される可用性キー アルゴリズムは次のとおりです。

- Exchange Online および Skype for Business 可用性キーは、AES-256 を使用します。

- SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーは、RSA-2048 を使用します。

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のキーを暗号化するために使用される暗号化暗号

![Exchange Online カスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online および OneDrive for Business のキーを暗号化するために使用される暗号化暗号

![SharePoint Online カスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)