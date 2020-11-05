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
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 eDiscovery ツールが電子メールメッセージに添付された暗号化ドキュメントを処理する方法について説明します。
ms.openlocfilehash: 89e6457015289055c56278f5f8650ce022ecf081
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920732"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子情報開示ツールの復号化

組織は暗号化テクノロジを使用して、組織内の機密コンテンツを保護し、適切な人物だけがそのコンテンツにアクセスできるようにします。 組織はさまざまな種類の暗号化を使用しており、Microsoft の暗号化テクノロジとサードパーティ製のテクノロジの両方を使用して、セキュリティ要件を満たし、機密情報を保護します。

今日、Microsoft 365 の電子情報開示ワークフローで暗号化されたコンテンツを管理するには、使用されている暗号化の種類とワークフローの特定の段階に応じて、暗号化されたアイテムを特別に処理する必要があります。 これは主に、コンテンツ検索、コア電子情報開示ケース、および高度な電子情報開示ケースからエクスポートされたときに電子メールメッセージのコンテンツを復号化することによって実現されました。 Microsoft 暗号化テクノロジで暗号化されたコンテンツは、エクスポートされるまでプレビューできませんでした。 高度な電子情報開示では、暗号化されたコンテンツに処理エラーがフラグが付けられ、暗号化されたアイテムをダウンロードして復号化し、復号化されたファイルをレビューセットにアップロードする必要がありました。

電子情報開示ワークフローで暗号化されたコンテンツを管理しやすくするために、Microsoft 365 eDiscovery ツールでは、電子メールメッセージに添付され、Exchange Online で送信される暗号化ファイルの暗号化を解除することができます。 この新しい機能の前に、rights management で保護された電子メールメッセージのコンテンツのみ (添付ファイルではない) の暗号化が解除されました。 これで、Microsoft 暗号化テクノロジを使用して暗号化されたファイルが検索条件に一致する電子メールメッセージに添付されている場合、その暗号化ファイルは、検索結果がプレビュー用に準備されたときに復号化されます。 これにより、電子情報開示マネージャーは、検索結果をプレビューする際に、暗号化された電子メール添付ファイルの内容を表示できます。

> [!NOTE]
> 2021年1月以降、Microsoft 365 eDiscovery ツールは、SharePoint Online と OneDrive for Business に格納されている暗号化されたドキュメントをサポートします。

## <a name="supported-encryption-technologies"></a>サポートされる暗号化テクノロジ

Microsoft の電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジには、Office メッセージの暗号化、Microsoft Information Protection (機密ラベル)、および Azure Rights Management があります。 Microsoft 暗号化テクノロジの詳細については、「 [暗号化](encryption.md)」を参照してください。 サードパーティの暗号化テクノロジで暗号化されたコンテンツはサポートされていません。 これには、Microsoft 以外のテクノロジで暗号化されたコンテンツをプレビューまたはエクスポートするときのサポートはありません。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、電子メール massages に添付された暗号化ファイルの暗号化をサポートする、Microsoft 365 電子情報開示ツールで実行されるタスクを示しています。 サポートタスクは、検索条件に一致する電子メールメッセージに添付された暗号化ファイルに対して実行できます。 値 "N/A" は、対応する電子情報開示ツールでは機能が使用できないことを示します。

|電子情報開示タスク  |コンテンツ検索  |コア電子情報開示  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|暗号化されたファイル内のコンテンツを検索する     |いいえ      |いいえ      |いいえ      |
|暗号化されたファイルのプレビュー     |はい      |はい     |必要       |
|検証セット内の暗号化ファイルを確認する    |N/A      |N/A        | はい        |
|暗号化されたファイルをエクスポートする    |はい       |はい  |必要    |

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化された添付ファイルをプレビュー、確認、エクスポートするには、RMS の暗号化解除の役割を割り当てられている必要があります。 また、Advanced 電子情報開示のレビューセットに追加された暗号化電子メール添付ファイルを確認してクエリを実行するには、この役割を割り当てる必要があります。

この役割は、既定では、Office 365 セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループに割り当てられます。 RMS の暗号化解除の役割の詳細については、「 [電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#rms-decrypt)」を参照してください。
