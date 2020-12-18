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
description: Microsoft 365 電子情報開示ツールが、電子メール メッセージに添付され、SharePoint Online と OneDrive for Business に保存された暗号化されたドキュメントを処理する方法について説明します。
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713268"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 電子情報開示ツールでの復号化

暗号化は、ファイル保護と情報保護戦略の重要な部分です。 すべての種類の組織は、暗号化テクノロジを使用して組織内の機密コンテンツを保護し、適切なユーザーだけがそのコンテンツにアクセスできます。

暗号化されたコンテンツに対して一般的な電子情報開示タスクを実行するために、電子情報開示マネージャーは、コンテンツ検索、コア電子情報開示ケース、および Advanced eDiscovery ケースからエクスポートされた電子メール メッセージ コンテンツを復号化する必要がありました。 Microsoft 暗号化テクノロジで暗号化されたコンテンツは、エクスポートされるまでレビューに利用できません。

電子情報開示ワークフローで暗号化されたコンテンツを簡単に管理するために、Microsoft 365 電子情報開示ツールには、電子メール メッセージに添付され、Exchange Online で送信される暗号化されたファイルの暗号化解除が組み込まれています。 さらに、SharePoint Online および OneDrive for Business に保存されている暗号化されたドキュメントは、Advanced eDiscovery で復号化されます。 

この新機能より前は、権限管理によって保護された (添付ファイルではなく) 電子メール メッセージのコンテンツだけが解読されました。 SharePoint と OneDrive の暗号化されたドキュメントは、電子情報開示ワークフロー中に解読できません。 Microsoft 暗号化テクノロジで暗号化されたファイルが電子メール メッセージに添付されている場合、または SharePoint または OneDrive アカウントに保存されている場合、検索結果のプレビュー準備、Advanced eDiscovery のレビュー セットへの追加、エクスポート時に暗号化されたアイテムの暗号化が解除されます。 これにより、電子情報開示管理者は、検索結果をプレビューするときに暗号化された電子メールの添付ファイルとサイト ドキュメントのコンテンツを表示し、Advanced eDiscovery のレビュー セットに追加された後に確認できます。

## <a name="supported-encryption-technologies"></a>サポートされている暗号化テクノロジ

Microsoft 電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。 これらのテクノロジには、Office Message Encryption、Azure Rights Management、Microsoft Information Protection (具体的には、区別ラベル) が含まれます。 Microsoft 暗号化テクノロジの詳細については、「暗号化」を [参照してください](encryption.md)。 サード パーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされていません。 たとえば、Microsoft 以外のテクノロジで暗号化されたコンテンツのプレビューやエクスポートはサポートされていません。

## <a name="ediscovery-activities-that-support-encrypted-items"></a>暗号化されたアイテムをサポートする電子情報開示アクティビティ

次の表は、SharePoint および OneDrive の電子メールの電子メールアドレスと暗号化されたドキュメントに添付された暗号化されたファイルに対して、Microsoft 365 電子情報開示ツールで実行できるサポートされているタスクを示しています。 これらのサポートされるタスクは、検索の条件に一致する暗号化されたファイルに対して実行できます。 値 "N/A" は、機能が対応する電子情報開示ツールで使用できない状態を示します。

|電子情報開示タスク  |コンテンツ検索  |コア電子情報開示  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|電子メールとサイト内の暗号化されたファイル内のコンテンツを検索する     |はい      |はい      |はい      |
|電子メールに添付された暗号化されたファイルをプレビューする     |はい      |はい     |はい       |
|SharePoint と OneDrive で暗号化されたドキュメントをプレビューする|いいえ      |いいえ    |はい       |
|レビュー セット内の暗号化されたファイルを確認する    |N/A      |N/A        | はい        |
|電子メールに添付された暗号化されたファイルをエクスポートする    |はい       |はい  |はい    |
|SharePoint と OneDrive で暗号化されたドキュメントをエクスポートする    |いいえ       |いいえ  |はい    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>電子情報開示での復号化の要件

Microsoft 暗号化テクノロジで暗号化されたファイルをプレビュー、確認、およびエクスポートするには、RMS 復号化の役割が割り当てられている必要があります。 また、Advanced eDiscovery のレビュー セットに追加された暗号化されたファイルを確認および照会するには、この役割を割り当てる必要があります。

この役割は、Office 365 セキュリティ/コンプライアンスセンターの [アクセス許可] ページの電子情報開示マネージャーの役割グループ&割り当てられます。 RMS 復号化役割の詳細については、「電子情報開示のアクセス許可を [割り当てる」を参照してください](assign-ediscovery-permissions.md#rms-decrypt)。
