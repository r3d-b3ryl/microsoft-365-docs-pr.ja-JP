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
description: Microsoft 365 eDiscovery ツールが電子メールメッセージに添付された暗号化ドキュメントを処理する方法について説明します。
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951120"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子情報開示ツールの復号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 すべての種類の組織は暗号化テクノロジを使用して、組織内の機密コンテンツを保護し、適切な人物だけがそのコンテンツにアクセスできるようにします。

暗号化されたコンテンツに対して一般的な電子情報開示タスクを実行するには、コンテンツ検索、コア電子情報開示ケース、および高度な電子情報開示ケースからエクスポートされたときに電子メールメッセージのコンテンツを解読するために電子情報開示マネージャーが必要でした。 Microsoft 暗号化テクノロジを使用して暗号化されたコンテンツは、エクスポートされるまで確認できませんでした。

電子情報開示ワークフローで暗号化されたコンテンツを管理しやすくするために、Microsoft 365 の電子情報開示ツールでは、電子メールメッセージに添付され、Exchange Online で送信される暗号化ファイルの復号化が組み込まれています。 この新しい機能の前に、rights management (および添付ファイルではない) で保護された電子メールメッセージのコンテンツのみが復号化されました。 これで、Microsoft 暗号化テクノロジを使用して暗号化されたファイルが検索条件に一致する電子メールメッセージに添付されている場合、その暗号化ファイルは、検索結果が確認のために準備されるときに復号化されます。 これにより、電子情報開示マネージャーは、検索結果をプレビューするときに暗号化された電子メール添付ファイルの内容を表示し、それらの添付ファイルを詳細な電子情報開示のレビューセットに追加した後に確認できます。

> [!NOTE]
> 近日 Microsoft 365 の電子情報開示ツールは、SharePoint Online および OneDrive for Business に格納されている暗号化されたドキュメントをサポートします。

## <a name="supported-encryption-technologies"></a>サポートされる暗号化テクノロジ

Microsoft の電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジには、Office メッセージの暗号化、Microsoft Information Protection (近日中)、および Azure Rights Management があります。 Microsoft 暗号化テクノロジの詳細については、「 [暗号化](encryption.md)」を参照してください。 サードパーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされません。 これには、Microsoft 以外のテクノロジで暗号化されたコンテンツをプレビューまたはエクスポートするときのサポートはありません。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、電子メール massages に添付された暗号化ファイルの暗号化をサポートする、Microsoft 365 電子情報開示ツールで実行されるタスクを示しています。 サポートタスクは、検索条件に一致する電子メールメッセージに添付された暗号化ファイルに対して実行できます。 値 "N/A" は、対応する電子情報開示ツールでは機能が使用できないことを示します。

|電子情報開示タスク  |コンテンツ検索  |コア電子情報開示  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|暗号化されたファイル内のコンテンツを検索する     |必要      |必要      |必要      |
|暗号化されたファイルのプレビュー     |必要      |必要     |必要       |
|検証セット内の暗号化ファイルを確認する    |N/A      |N/A        | はい        |
|暗号化されたファイルをエクスポートする    |必要       |必要  |必要    |

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化された添付ファイルをプレビュー、確認、エクスポートするには、RMS の暗号化解除の役割を割り当てられている必要があります。 また、Advanced 電子情報開示のレビューセットに追加された暗号化電子メール添付ファイルを確認してクエリを実行するには、この役割を割り当てる必要があります。

この役割は、既定では、Office 365 セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループに割り当てられます。 RMS の暗号化解除の役割の詳細については、「 [電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#rms-decrypt)」を参照してください。
