---
title: 電子情報開示での復号化
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 電子情報開示ツールMicrosoft 365電子メール メッセージに添付された暗号化されたドキュメントを処理し、SharePoint Online および OneDrive for Businessに保存する方法について説明します。
ms.openlocfilehash: 9d3bee507d2add2a6ad1dedadf64c47298ecbab6
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567310"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>電子情報開示ツールMicrosoft 365復号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 すべての種類の組織では、暗号化テクノロジを使用して組織内の機密性の高いコンテンツを保護し、適切なユーザーだけがそのコンテンツにアクセスできます。

暗号化されたコンテンツで一般的な電子情報開示タスクを実行するには、電子情報開示マネージャーは、コンテンツ検索、コア電子情報開示ケース、および Advanced eDiscovery ケースからエクスポートされた電子メール メッセージコンテンツを復号化する必要がありました。 Microsoft 暗号化テクノロジで暗号化されたコンテンツは、エクスポートされるまでレビューに使用できません。

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールは、電子メール メッセージに添付され、Exchange Online で送信される暗号化されたファイルの暗号化解除を組み込むになりました。<sup>1</sup>さらに、SharePointに保存されている暗号化SharePoint、OneDrive for Businessで暗号化解除Advanced eDiscovery。

この新しい機能の前に、権限管理によって保護された電子メール メッセージのコンテンツ (および添付されていないファイル) だけが復号化されました。 電子情報開示ワークフロー SharePoint OneDrive暗号化されたドキュメントを暗号化解除できません。 これで、Microsoft 暗号化テクノロジで暗号化されたファイルは、検索結果がプレビュー用に準備され、Advanced eDiscovery でレビュー セットに追加され、エクスポートされた場合に、SharePoint または OneDrive アカウント上に検索および復号化されます。 さらに、電子メール メッセージにSharePoint OneDrive、暗号化されたドキュメントを検索できます。 この復号化機能を使用すると、電子情報開示管理者は、検索結果をプレビューするときに暗号化された電子メール添付ファイルとサイト ドキュメントのコンテンツを表示し、Advanced eDiscovery のレビュー セットに追加された後で確認できます。

## <a name="supported-encryption-technologies"></a>サポートされている暗号化テクノロジ

Microsoft 電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジは、Azure Rights Management と Microsoft Information Protection (特に感度ラベル) です。 Microsoft 暗号化テクノロジの詳細については、「暗号化」を [参照してください](encryption.md)。 サードパーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされていません。 たとえば、Microsoft 以外のテクノロジで暗号化されたコンテンツのプレビューやエクスポートはサポートされていません。

> [!NOTE]
> Microsoft 電子情報開示ツールでは、Office 365 Message Encryption (OME) で暗号化された電子メール メッセージの暗号化解除はサポートされていません。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、Microsoft 365 SharePoint および OneDrive の電子メール メッセージおよび暗号化されたドキュメントに添付された暗号化されたファイルに対して Microsoft 365 電子情報開示ツールで実行できるサポートされているタスクを示しています。 これらのサポートされているタスクは、検索の条件に一致する暗号化されたファイルに対して実行できます。 値は `N/A` 、対応する電子情報開示ツールで機能が使用できない状態を示します。

|電子情報開示タスク  |コンテンツ検索  |コア電子情報開示  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|電子メールとサイト内の暗号化されたファイル内のコンテンツを検索<sup>する 1</sup>     |はい      |はい      |はい      |
|メールに添付された暗号化されたファイルをプレビューする     |はい      |はい     |はい       |
|暗号化されたドキュメントをプレビュー SharePointとOneDrive|いいえ      |いいえ    |はい       |
|レビュー セット内の暗号化されたファイルを確認する    |該当なし      |該当なし        | はい        |
|電子メールに添付された暗号化されたファイルをエクスポートする    |はい       |はい  |はい    |
|暗号化されたドキュメントを、SharePointおよびOneDrive    |いいえ       |いいえ  |はい    |
|||||

> [!NOTE]
> <sup>1</sup>ローカル コンピューター上に (SharePoint または OneDrive サイトに保存されていない) 暗号化されたファイルは、電子情報開示のインデックスが作成されません。 つまり、暗号化されたローカル ファイルが電子メール メッセージに添付されている場合、ファイルに検索クエリに一致するキーワードが含まれている場合でも、キーワード検索クエリによってファイルが返されません。 ただし、電子情報開示検索では、電子メール プロパティ (送信日、送信者、受信者、件名など) が検索クエリと一致する場合、ローカル暗号化ファイルを含む電子メール メッセージを返す可能性があります。

### <a name="decryption-limitations-with-sensitivity-labels"></a>秘密度ラベルの復号化の制限

暗号化を適用した感度ラベルが次のいずれかの設定で構成されている場合、電子情報開示は SharePoint および OneDrive の暗号化ファイルをサポートしません。

- ユーザーは、ラベルを手動でドキュメントに適用するときにアクセス許可を割り当てできます。 これは、ユーザー定義の *アクセス許可と呼ばれる場合があります*。

- ドキュメントへのユーザー アクセスには、有効期限設定が [Never] 以外の値に **設定されています**。

これらの設定の詳細については、「暗号化の適用に感度ラベルを使用してコンテンツへのアクセスを制限する」の「暗号化設定の構成 [」セクションを参照してください](encryption-sensitivity-labels.md#configure-encryption-settings)。

以前の設定で暗号化されたドキュメントは、引き続き電子情報開示検索によって返されます。 これは、ドキュメント プロパティ (タイトル、作成者、変更日など) が検索条件と一致する場合に発生する可能性があります。 これらのドキュメントは検索結果に含まれている可能性があります。プレビューやレビューは行えません。 これらのドキュメントは、エクスポート時も暗号化されたままAdvanced eDiscovery。

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化されたファイルをプレビュー、確認、およびエクスポートするには、RMS Decrypt ロールを割り当てる必要があります。 また、このロールを割り Advanced eDiscovery当てる必要があります。

この役割は、コンプライアンス センターの [セキュリティ] ページの[アクセス許可] ページの電子情報開示マネージャー Office 365既定&割り当てられます。 RMS 復号化の役割の詳細については、「電子情報開示の [アクセス許可を割り当てる」を参照してください](assign-ediscovery-permissions.md#rms-decrypt)。
