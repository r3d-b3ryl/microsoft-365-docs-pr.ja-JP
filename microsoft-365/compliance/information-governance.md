---
title: Microsoft 365 の情報ガバナンスの詳細
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
description: Microsoft 365 を使用して組織のデータを管理することの意味について説明します。
ms.openlocfilehash: c9661aadcef5d70b4099cb44e0fa054ab27e5562
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242226"
---
# <a name="learn-about-information-governance"></a>情報ガバナンスの詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[記録管理](records-management.md)と[データ コネクタ](archiving-third-party-data.md)を含む [Microsoft 情報ガバナンス](manage-information-governance.md)の一部として、Microsoft 365 の情報ガバナンスには、保持する必要のあるコンテンツを保持し、必要のないコンテンツを削除するためのツールと機能が用意されています。 コンテンツの保持と削除は、コンプライアンスや規制要件のために必要な場合が多いですが、ビジネス価値のなくなったコンテンツを削除することは、リスクや責任の管理にも役立ちます。 たとえば、攻撃面を減らします。

**アイテム保持ポリシー** は、情報ガバナンスの礎石となるものです。 これらを Exchange、SharePoint、OneDrive、Teams、Yammer などの Microsoft 365 ワークロードに使用できます。 これらのサービスのコンテンツを無期限に保持するか、ユーザーが編集や削除を行った場合に特定の期間保持するかを構成します。 あるいは、指定した期間の経過後、コンテンツがまだ削除されていない場合は、自動的に完全に削除するようにポリシーを構成することもできます。 この 2 つのアクションを組み合わせて、保持してから削除することも可能で、これは非常に一般的な構成です。 たとえば、メールを 3 年間保持してから削除します。

アイテム保持ポリシーを構成する場合は、組織内のすべてのインスタンス (すべてのメールボックス、すべての SharePoint サイトなど)、または個々のインスタンス (特定の部署や地域のメールボックスのみ、選択した SharePoint サイトなど) を対象とすることができます。

法的文書の保持期間を長くするなど、個々のメールやドキュメントに例外が必要な場合は、**保持ラベル** をアプリに発行してユーザーが適用できるようにしたり、コンテンツを検査して自動的に適用したりします。

アイテム保持ポリシー、保持ラベル、および Microsoft 365 内のデータ保持の仕組みに関する詳細情報については、「[アイテム保持ポリシーおよび保持ラベルの詳細](retention.md)」をご覧ください。 

> [!NOTE]
> ビジネス、法務、または規制上の記録保持要件のために貴重品のライフサイクル管理が必要な場合は、情報ガバナンスを用いた保持ラベルではなく、[記録管理](records-management.md)を用いた保持ラベルを使用してください。

必要な情報を保持し、不要な情報を削除するのに役立つその他の情報ガバナンス機能。

- **メールボックス アーカイブ** では、ユーザーに追加のメールボックス記憶領域を提供し、100 GB 以上のストレージを必要とするメールボックスには自動拡張アーカイビングを提供します。 既定のアーカイブ ポリシーでは、メールがアーカイブ メールボックスに自動的に移動され、必要に応じてこのポリシーをカスタマイズできます。 メールボックス アーカイブの詳細については、「[メールボックスのアーカイブに関する詳細情報](archive-mailboxes.md)」を参照してください。
    
- **非アクティブなメールボックス** では、従業員が組織を離れた後もメールボックスのコンテンツを保持します。 非アクティブなメールボックスの詳細については、「[非アクティブなメールボックスに関する詳細情報](inactive-mailboxes-in-office-365.md)」を参照してください。

- ネットワーク アップロードまたはドライブ送付を使用して、**PST ファイルのサービスをインポート** します。 詳細については、「[組織の PST ファイルのインポートに関する詳細情報](importing-pst-files-to-office-365.md)」を参照してください。

## <a name="deployment-guidance"></a>展開ガイダンス

推奨される展開ロードマップ、ライセンス情報、アクセス許可、サポートされているシナリオとエンドユーザー ドキュメントのリソースのリストを含む情報ガバナンスの展開ガイダンスについては、「[情報ガバナンスを開始する](get-started-with-information-governance.md)」を参照してください。

データを保護するための展開ガイダンスをお探しですか? 「[Microsoft の情報保護ソリューションの展開](information-protection-solution.md)」を参照してください。

