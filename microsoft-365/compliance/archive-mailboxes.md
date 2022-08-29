---
title: Microsoft Purview のためのアーカイブ メールボックスの詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 追加のメールボックス ストレージを提供するアーカイブ メールボックスについて説明します。
ms.openlocfilehash: 53967fbb829cdedddbadc0de9158d18330e71969
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359145"
---
# <a name="learn-about-archive-mailboxes"></a>アーカイブ メールボックスの詳細

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft Purview でのメールボックスのアーカイブは、 *インプレース アーカイブ* とも呼ばれ、ユーザーに追加のメールボックスストレージ領域を提供します。 アーカイブ メールボックスをオンにすると、ユーザーの現在のメールボックスが *プライマリ メールボックス* になり、*アーカイブ メールボックス* と呼ばれる追加のメールボックスが作成されます。 どちらのメールボックスも、Microsoft Purview コンプライアンス ポータルからのコンテンツ検索、Microsoft 365 データ保持、訴訟ホールドなどのコンプライアンス機能に関するユーザーのメールボックスとみなされます。

ユーザーは、Outlook と Outlook on the web を使用してアーカイブ メールボックスにアクセスし、メッセージを保存できます。 ユーザーは、自分のプライマリ メールボックスとアーカイブ メールボックスの間でメッセージを移動したりコピーしたりもできます。 ユーザーはまた、削除済みアイテムの復元ツールを使用して、アーカイブ メールボックスの [回復可能なアイテム] フォルダーから削除済みのアイテムを復元できます。

## <a name="managing-archive-mailboxes-with-messaging-records-management-mrm"></a>メッセージング レコード管理 (MRM) を使用したアーカイブ メールボックスの管理

メッセージは、メッセージング レコード管理 (MRM) の [既定の Exchange アイテム保持ポリシー](/exchange/security-and-compliance/messaging-records-management/default-retention-policy) によってアーカイブ メールボックスに移動することもできます。 この既定のポリシーは、すべてのメールボックスに自動的に割り当てられ、次の処理を行います。

  - 2 年間以上経過したアイテムを、ユーザーのプライマリ メールボックスからアーカイブ メールボックスに移動します。

  - 14 日以上経過したアイテムを、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーから、アーカイブ メールボックスの [回復可能なアイテム] フォルダーへ自動的に移動します

[保持タグ](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)を使用して組織の MRM ポリシー をカスタマイズできます。 構成例については、「[組織のメールボックスのアーカイブと削除ポリシーを設定する](set-up-an-archive-and-deletion-policy-for-mailboxes.md)」を参照してください。

> [!NOTE]
> MRM は、Microsoft 365 のアイテム保持ポリシーや保持ラベルと同様に、指定した期間を経過したメールを自動的に削除することもできます。 Microsoft 365 保持よりも古いテクノロジとして、MRM は Microsoft Purview のアイテム保持ポリシーや保持ラベルと並行して動作し続けます。 詳細については、「[以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features)」を参照してください。

## <a name="auto-expanding-archiving"></a>自動拡張アーカイブ 

ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。 ユーザーがより多くの記憶領域を必要とする場合、自動拡張アーカイブを有効にして、アーカイブ メールボックスに最大 1.5 TB の追加記憶域を提供します。 詳細については、「[自動拡張アーカイブの詳細](autoexpanding-archiving.md)」を参照してください。

## <a name="next-steps"></a>次の手順

「[Microsoft Purview コンプライアンス ポータルでアーカイブ メールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。
