---
title: 電子情報開示での復号化
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 電子情報開示ツールが、電子メール メッセージに添付され、SharePoint Online およびOneDrive for Businessに保存された暗号化されたドキュメントを処理する方法について説明します。
ms.openlocfilehash: bec0b4c600f3bb7b08d10f2b32b00edb627a1165
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798085"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子情報開示ツールでの復号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 あらゆる種類の組織では、暗号化テクノロジを使用して組織内の機密コンテンツを保護し、適切なユーザーのみがそのコンテンツにアクセスできるようにします。

暗号化されたコンテンツに対して一般的な電子情報開示タスクを実行するには、電子情報開示マネージャーは、コンテンツ検索、Microsoft Purview eDiscovery (Standard) ケース、Microsoft Purview eDiscovery (Premium) ケースからエクスポートされた電子メール メッセージ コンテンツを復号化する必要がありました。 Microsoft 暗号化テクノロジで暗号化されたコンテンツは、エクスポート後まで確認できませんでした。

電子情報開示ワークフローで暗号化されたコンテンツを管理しやすくするために、Microsoft 365 電子情報開示ツールは、電子メール メッセージに添付され、Exchange Onlineで送信された暗号化されたファイルの暗号化解除を組み込むようになりました。<sup>1</sup> さらに、SharePoint Online とOneDrive for Businessに格納された暗号化されたドキュメントは、電子情報開示 (Premium)<sup>2</sup> で暗号化解除されます。

この新しい機能の前に、権限管理によって保護された (添付ファイルではなく) 電子メール メッセージのコンテンツのみが暗号化解除されました。 SharePoint と OneDrive の暗号化されたドキュメントは、電子情報開示ワークフロー中に暗号化を解除できませんでした。 これで、Microsoft 暗号化テクノロジで暗号化されたファイルが SharePoint または OneDrive アカウントに配置され、検索結果がプレビュー用に準備され、電子情報開示 (Premium) のレビュー セットに追加され、エクスポートされたときに、検索および暗号化解除されます。 さらに、(コピーとして) 電子メール メッセージに添付されている SharePoint と OneDrive の暗号化されたドキュメントは検索可能です。 この復号化機能を使用すると、電子情報開示マネージャーは、検索結果をプレビューするときに、暗号化された電子メールの添付ファイルとサイト ドキュメントのコンテンツを表示し、電子情報開示 (Premium) のレビュー セットに追加した後で確認できます。

## <a name="supported-encryption-technologies"></a>サポートされている暗号化テクノロジ

Exchange の場合、Microsoft 電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジは、Azure Rights Management (Azure RMS)<sup>3</sup> とMicrosoft Purview 情報保護 (特に秘密度ラベル) です。 Microsoft 暗号化テクノロジの詳細については、 [暗号化](encryption.md) と使用可能なさまざまな [電子メール暗号化](email-encryption.md#comparing-email-encryption-options-available-in-office-365) オプションに関するページを参照してください。 S/MIME またはサード パーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされていません。 たとえば、Microsoft 以外のテクノロジで暗号化されたコンテンツのプレビューまたはエクスポートはサポートされていません。

> [!NOTE]
> [Microsoft Purview Message Encryption カスタム ブランド テンプレート](add-your-organization-brand-to-encrypted-messages.md)で送信された電子メール メッセージの暗号化解除は、Microsoft 電子情報開示ツールではサポートされていません。 OME カスタム ブランド テンプレートを使用する場合、電子メール メッセージは受信者のメールボックスの代わりに OME ポータルに配信されます。 そのため、電子情報開示ツールを使用して暗号化されたメッセージを検索することはできません。

SharePoint の場合、SharePoint Online サービスでラベル付けされたコンテンツは復号化されます。 SharePoint、従来のドキュメント ライブラリ RMS テンプレートまたは設定、S/MIME またはその他の標準にアップロードする前に、クライアントでラベル付けまたは暗号化されたアイテムはサポートされていません<sup>2</sup>。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、SharePoint と OneDrive の電子メール メッセージと暗号化されたドキュメントに添付された暗号化されたファイルに対して Microsoft 365 電子情報開示ツールで実行できるサポートされているタスクを示しています。 これらのサポートされているタスクは、検索の条件に一致する暗号化されたファイルに対して実行できます。 値は `N/A` 、対応する電子情報開示ツールで機能が使用できないことを示します。

|電子情報開示タスク  |コンテンツ検索  |電子情報開示 (標準)  |電子情報開示 (プレミアム)  |
|:---------|:---------|:---------|:---------|
|サイトと電子メールの添付ファイル内の暗号化されたファイル内のコンテンツを検索<sup>する 1</sup>     |いいえ      |いいえ      |はい      |
|電子メールに添付された暗号化されたファイルをプレビューする     |はい      |はい     |はい       |
|SharePoint と OneDrive で暗号化されたドキュメントをプレビューする|いいえ      |いいえ    |はい       |
|レビュー セット内の暗号化されたファイルを確認する    |該当なし      |該当なし        | はい        |
|電子メールに添付された暗号化されたファイルをエクスポートする    |はい       |はい  |はい    |
|SharePoint と OneDrive で暗号化されたドキュメントをエクスポートする    |いいえ       |いいえ  |はい    |
|||||

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>SharePoint と OneDrive の秘密度ラベルを使用した復号化の制限

暗号化を適用した秘密度ラベルが次のいずれかの設定で構成されている場合、電子情報開示では SharePoint と OneDrive の暗号化されたファイルはサポートされません。

- ユーザーは、ドキュメントにラベルを手動で適用するときにアクセス許可を割り当てることができます。 これは *、ユーザー定義のアクセス許可* と呼ばれることもあります。

- ドキュメントへのユーザー アクセスには、期限切れの設定があり、この設定は **[なし]** 以外の値に設定されます。

これらの設定の詳細については、「 [秘密度ラベルを使用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md#configure-encryption-settings)」の「暗号化設定を構成する」セクションを参照してください。

以前の設定で暗号化されたドキュメントは、電子情報開示検索で引き続き返すことができます。 これは、ドキュメント プロパティ (タイトル、作成者、変更日など) が検索条件と一致する場合に発生する可能性があります。 これらのドキュメントは検索結果に含まれる場合がありますが、プレビューや確認はできません。 これらのドキュメントは、電子情報開示 (Premium) でエクスポートされるときにも暗号化されたままになります。

> [!IMPORTANT]
> 暗号化解除は、ローカルで暗号化され、SharePoint または OneDrive にアップロードされるファイルではサポートされていません。 たとえば、Azure Information Protection (AIP) クライアントによって暗号化され、Microsoft 365 にアップロードされたローカル ファイルはサポートされていません。 暗号化解除では、SharePoint または OneDrive サービスで暗号化されたファイルのみがサポートされます。

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化されたファイルをプレビュー、確認、エクスポートするには、RMS Decrypt ロールを割り当てる必要があります。 また、電子情報開示 (Premium) のレビュー セットに追加された暗号化されたファイルを確認してクエリを実行するには、このロールを割り当てる必要があります。

このロールは、Microsoft Purview コンプライアンス ポータルの **[アクセス許可]** ページの電子情報開示マネージャーの役割グループに既定で割り当てられます。 RMS Decrypt ロールの詳細については、「 [電子情報開示アクセス許可の割り当て](assign-ediscovery-permissions.md#rms-decrypt)」を参照してください。

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-ediscovery-standard"></a>コンテンツ検索または電子情報開示を使用した RMS で保護された電子メール メッセージと暗号化された添付ファイルの暗号化解除 (Standard)

コンテンツ検索の結果に含まれる権限で保護された (RMS で保護された) 電子メール メッセージは、エクスポートすると暗号化が解除されます。 さらに、 [Microsoft 暗号化テクノロジ](encryption.md) で暗号化され、検索結果に含まれる電子メール メッセージに添付されているファイルは、エクスポート時に暗号化解除されます。 この復号化機能は、電子情報開示マネージャー役割グループのメンバーに対して既定で有効になっています。 これは、RMS 復号化管理ロールが既定でこの役割グループに割り当てられているためです。 暗号化された電子メール メッセージと添付ファイルをエクスポートする場合は、次の点に注意してください。
  
- 前述のように、RMS で保護されたメッセージをエクスポートするときに復号化を有効にする場合は、検索結果を個々のメッセージとしてエクスポートする必要があります。 検索結果を PST ファイルにエクスポートすると、RMS で保護されたメッセージは個々の電子メール メッセージとしてエクスポートされます。

- 復号化されたメッセージは、 **ResultsLog** レポートで識別されます。 このレポートには **デコード状態** という名前の列が含まれており、 **デコードされた** 値は復号化されたメッセージを識別します。

- 検索結果をエクスポートするときに添付ファイルの暗号化を解除するだけでなく、検索結果をプレビューするときに復号化されたファイルをプレビューすることもできます。 権限で保護された電子メール メッセージは、エクスポート後にのみ表示できます。

- 他のユーザーが RMS で保護されたメッセージと暗号化されたファイルの添付ファイルを復号化できないようにする必要がある場合は、(組み込みの電子情報開示マネージャーの役割グループをコピーして) カスタム役割グループを作成し、カスタム ロール グループから RMS 復号化管理ロールを削除する必要があります。 次に、メッセージを復号化しないユーザーをカスタム ロール グループのメンバーとして追加します。

## <a name="notes"></a>メモ

<sup>1</sup> ローカル コンピューター上にあり、電子メール メッセージにコピーされた暗号化されたファイルは、電子情報開示の暗号化解除およびインデックス付けされません。 電子情報開示 (Premium) の場合、暗号化解除するには、受信者メールボックス内の暗号化された電子メールと添付ファイルに高度なインデックスを作成する必要があります。 高度なインデックス作成の詳細については、「 [カストディアン データの高度なインデックス作成](indexing-custodian-data.md)」を参照してください。

<sup>2</sup> SharePoint Online サービス内でラベル付けされたアイテムのみが暗号化解除されます。アップロード前のクライアントでのラベル付けや暗号化、従来のドキュメント ライブラリ RMS テンプレートまたは設定、SMIME またはその他の標準など、その他はすべてサポートされていません。 [Office ファイルの秘密度ラベルを有効にする方法に関するページを](sensitivity-labels-sharepoint-onedrive-files.md)参照してください。

<sup>3</sup> RMS キーは M365/O365 クラウド サービスで完全に管理する必要があります。つまり、DKE、BYOK、OnPrem RMS などはサポートされていません。 [Azure Information Protection テナント キーを](/azure/information-protection/plan-implement-tenant-key#tenant-root-keys-generated-by-microsoft)参照してください。
