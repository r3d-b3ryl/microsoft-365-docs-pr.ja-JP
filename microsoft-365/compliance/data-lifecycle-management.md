---
title: Microsoft Purview データ ライフサイクル管理の詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
description: Microsoft Purview データ ライフサイクル管理を利用することで、必要なものを保持して、不要なものを削除する方法について説明します。
ms.openlocfilehash: 6252bb9824a534ffca5f295bf9f9c54816bcb320
ms.sourcegitcommit: a1c86e51f6fec7517356251c3b99b1a86705c8c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2022
ms.locfileid: "67336690"
---
# <a name="learn-about-data-lifecycle-management"></a>データ ライフサイクル管理の詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft Purview データ ライフサイクル管理 (旧称: Microsoft 情報ガバナンス) には、保持が必要なコンテンツを保持して、保持が不要なコンテンツを削除するためのツールと機能が用意されています。 

コンテンツの保持と削除は、コンプライアンスや規制要件のために必要な場合が多いですが、ビジネス価値のなくなったコンテンツを削除することは、リスクや責任の管理にも役立ちます。 たとえば、攻撃面を減らします。

## <a name="microsoft-365-features"></a>Microsoft 365 の機能

**保持ポリシー** は、データ ライフサイクル管理の基盤です。 このポリシーは Exchange、SharePoint、OneDrive、Teams、Yammer などの Microsoft 365 ワークロードに使用できます。 これらのサービスのコンテンツを無期限に保持するか、ユーザーが編集や削除を行った場合に特定の期間保持するかを構成します。 あるいは、指定した期間の経過後、コンテンツがまだ削除されていない場合は、自動的に完全に削除するようにポリシーを構成することもできます。 この 2 つのアクションを組み合わせて、保持してから削除することも可能で、これは非常に一般的な構成です。 たとえば、メールを 3 年間保持してから削除します。

アイテム保持ポリシーを構成する場合は、組織内のすべてのインスタンス (すべてのメールボックス、すべての SharePoint サイトなど)、または個々のインスタンス (特定の部署や地域のメールボックスのみ、選択した SharePoint サイトなど) を対象とすることができます。

法的文書の保持期間を長くするなど、個々のメールやドキュメントに例外が必要な場合は、**保持ラベル** をアプリに発行してユーザーが適用できるようにしたり、コンテンツを検査して自動的に適用したりします。

アイテム保持ポリシー、保持ラベル、および Microsoft 365 内のデータ保持の仕組みに関する詳細情報については、「[アイテム保持ポリシーおよび保持ラベルの詳細](retention.md)」をご覧ください。 

> [!NOTE]
> ビジネス、法律、または規制の記録保持要件にとって重要度の高いアイテムの管理が必要な場合は、データ ライフサイクル管理で保持ラベルを使用するのではなく、[レコード管理](records-management.md)で保持ラベルを使用します。

必要なものを保持して不要なものを削除する際に役立つ、その他のデータ ライフサイクル管理機能を次に示します。

- **メールボックス アーカイブ** では、ユーザーに追加のメールボックス記憶領域を提供し、100 GB 以上のストレージを必要とするメールボックスには自動拡張アーカイビングを提供します。 既定のアーカイブ ポリシーでは、メールがアーカイブ メールボックスに自動的に移動され、必要に応じてこのポリシーをカスタマイズできます。 メールボックス アーカイブの詳細については、「[メールボックスのアーカイブに関する詳細情報](archive-mailboxes.md)」を参照してください。
    
- **非アクティブなメールボックス** では、従業員が組織を離れた後もメールボックスのコンテンツを保持します。 非アクティブなメールボックスの詳細については、「[非アクティブなメールボックスに関する詳細情報](inactive-mailboxes-in-office-365.md)」を参照してください。

- ネットワーク アップロードまたはドライブ送付を使用して、**PST ファイルのサービスをインポート** します。 詳細については、「[組織の PST ファイルのインポートに関する詳細情報](importing-pst-files-to-office-365.md)」を参照してください。

## <a name="exchange-legacy-features"></a>Exchange (レガシ) 機能

メッセージング レコード管理 (MRM) の **アイテム保持ポリシーと保持タグ**、および **履歴管理ルール** は、従来の Exchange 管理センターから最初に構成できた Exchange の以前のコンプライアンス機能です。 [新しい Exchange 管理センター](/exchange/features-in-new-eac)に移行されていません。

これらの機能をまだ使用していない場合、またはデータ ライフサイクル管理に Microsoft 365 機能の代わりに使用する特定のビジネス要件がある場合は、これらの古いコンプライアンス機能を使用することはお勧めしません。 代わりに、データを保持し、他の Microsoft 365 サービス全体のポリシーをサポートする新しい Microsoft 365 機能を使用してください。

詳細については、「[以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features)」を参照してください。


## <a name="deployment-guidance"></a>展開ガイダンス

データ ライフサイクル管理の展開について、推奨される展開のロードマップ、ライセンス情報、アクセス許可、サポートされているシナリオとエンドユーザー ドキュメントのリストなどのガイダンスは、「[データ ライフサイクル管理の使用を開始する](get-started-with-information-governance.md)」を参照してください。

データを保護するための展開ガイダンスをお探しですか? 「[Microsoft Purview を使用した情報保護ソリューションを展開する](information-protection-solution.md)」を参照してください。

