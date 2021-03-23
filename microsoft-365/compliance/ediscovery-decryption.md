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
description: Microsoft 365 電子情報開示ツールが電子メール メッセージに添付され、SharePoint Online および OneDrive for Business に保存された暗号化されたドキュメントを処理する方法について説明します。
ms.openlocfilehash: ad7ee9816e83caa49e437e1723655162a44c93fa
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034070"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子情報開示ツールでの復号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 すべての種類の組織では、暗号化テクノロジを使用して組織内の機密性の高いコンテンツを保護し、適切なユーザーだけがそのコンテンツにアクセスできます。

暗号化されたコンテンツで一般的な電子情報開示タスクを実行するために、電子情報開示マネージャーは、コンテンツ検索、コア電子情報開示ケース、および高度な電子情報開示ケースからエクスポートされた電子メール メッセージコンテンツを復号化する必要がありました。 Microsoft 暗号化テクノロジで暗号化されたコンテンツは、エクスポートされるまでレビューに使用できません。

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールは、電子メール メッセージに添付され、Exchange Online で送信される暗号化されたファイルの暗号化解除を組み込むになりました。 さらに、SharePoint Online および OneDrive for Business に格納されている暗号化されたドキュメントは、Advanced eDiscovery で復号化されます。

この新しい機能の前に、権限管理によって保護された電子メール メッセージのコンテンツ (および添付されていないファイル) だけが復号化されました。 SharePoint および OneDrive の暗号化されたドキュメントは、電子情報開示ワークフロー中に解読できません。 これで、Microsoft 暗号化テクノロジで暗号化されたファイルが電子メール メッセージに添付されている場合、または SharePoint または OneDrive アカウント上にある場合、検索結果がプレビュー用に準備され、Advanced eDiscovery のレビュー セットに追加されてエクスポートされた場合、暗号化されたアイテムは復号化されます。 これにより、電子情報開示管理者は、検索結果のプレビュー時に暗号化された電子メール添付ファイルとサイト ドキュメントのコンテンツを表示し、Advanced eDiscovery のレビュー セットに追加された後で確認できます。

## <a name="supported-encryption-technologies"></a>サポートされている暗号化テクノロジ

Microsoft 電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジは、Azure Rights Management と Microsoft Information Protection (特に感度ラベル) です。 Microsoft 暗号化テクノロジの詳細については、「暗号化」を [参照してください](encryption.md)。 サードパーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされていません。 たとえば、Microsoft 以外のテクノロジで暗号化されたコンテンツのプレビューやエクスポートはサポートされていません。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、SharePoint および OneDrive の電子メール メッセージおよび暗号化されたドキュメントに添付された暗号化されたファイルに対して Microsoft 365 電子情報開示ツールで実行できるサポートされているタスクを示しています。 これらのサポートされているタスクは、検索の条件に一致する暗号化されたファイルに対して実行できます。 値は `N/A` 、対応する電子情報開示ツールで機能が使用できない状態を示します。

|電子情報開示タスク  |コンテンツ検索  |コア電子情報開示  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|電子メールとサイト内の暗号化されたファイル内のコンテンツを検索する     |はい      |はい      |はい      |
|メールに添付された暗号化されたファイルをプレビューする     |はい      |はい     |はい       |
|SharePoint と OneDrive で暗号化されたドキュメントをプレビューする|いいえ      |いいえ    |はい       |
|レビュー セット内の暗号化されたファイルを確認する    |該当なし      |該当なし        | はい        |
|電子メールに添付された暗号化されたファイルをエクスポートする    |はい       |はい  |はい    |
|SharePoint および OneDrive で暗号化されたドキュメントをエクスポートする    |いいえ       |いいえ  |はい    |
|||||

**注:** 暗号化を適用した感度ラベルが次のいずれかの設定で構成されている場合、電子情報開示は SharePoint と OneDrive の暗号化ファイルをサポートしません。

- ユーザーは、ラベルを手動でドキュメントに適用するときにアクセス許可を割り当てできます。 これは、ユーザー定義の *アクセス許可と呼ばれる場合があります*。<br/>

- ドキュメントへのユーザー アクセスには、有効期限設定が [Never] 以外の値に **設定されています**。

これらの設定の詳細については、「暗号化の適用に感度ラベルを使用してコンテンツへのアクセスを制限する」の「暗号化設定の構成 [」セクションを参照してください](encryption-sensitivity-labels.md#configure-encryption-settings)。

以前の設定で暗号化されたドキュメントは、引き続き電子情報開示検索によって返されます。 これは、ドキュメント プロパティ (タイトル、作成者、変更日など) が検索条件と一致する場合に発生する可能性があります。 これらのドキュメントは検索結果に含まれている可能性があります。プレビューやレビューは行えません。 これらのドキュメントは、高度な電子情報開示でエクスポートされた場合も暗号化されたままです。

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化されたファイルをプレビュー、確認、およびエクスポートするには、RMS Decrypt ロールを割り当てる必要があります。 また、Advanced eDiscovery のレビュー セットに追加される暗号化されたファイルを確認してクエリするには、この役割を割り当てる必要があります。

この役割は、既定では、コンプライアンス センターの [Office  365 セキュリティ] ページの [&マネージャー] 役割グループに割り当てられます。 RMS 復号化の役割の詳細については、「電子情報開示の [アクセス許可を割り当てる」を参照してください](assign-ediscovery-permissions.md#rms-decrypt)。
