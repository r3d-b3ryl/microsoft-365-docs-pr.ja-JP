---
title: Exchange のアイテム保持の詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Exchange メールと Exchange パブリック フォルダーに特に適用される保持動作について説明します。
ms.openlocfilehash: aa4142db2114b2b58cc391429f1389c6b9fad52d
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049895"
---
# <a name="learn-about-retention-policies-for-exchange"></a>Exchange のアイテム保持ポリシーの詳細

この記事の情報は、Exchange に固有の情報が含まれているため、「[アイテム保持ポリシーの詳細](retention-policies.md)」を補足するものです。

## <a name="how-a-retention-policy-works-with-exchange-locations"></a>アイテム保持ポリシーは Exchange に対してどのように作用するか

ユーザーのメール、予定表、その他のアイテムでは、アイテム保持ポリシーはメールボックス レベルで適用されます。

パブリック フォルダーでは、アイテム保持ポリシーはメールボックス レベルではなく、フォルダー レベルで適用されます。 

メールボックスとパブリック フォルダーの両方とも、アイテムを保持するために、[[回復可能なアイテム] フォルダー](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) を使用します。 電子情報開示のアクセス許可を割り当てられているユーザーだけが、他のユーザーの [回復可能なアイテム] フォルダーのアイテムを表示できます。
  
既定では、削除済みアイテム フォルダー以外のフォルダーからメッセージを削除すると、そのメッセージは削除済みアイテム フォルダーに移動されます。 ユーザーが [削除済みアイテム] フォルダー内のアイテムを削除すると、メッセージは [回復可能なアイテム] フォルダーに移動されます。 ただし、ユーザーは、任意のフォルダー内のアイテムを論理的な削除 (Shift + Delete) ができます。これにより、削除済みアイテム フォルダーがバイパスされ、アイテムが回復可能なアイテム フォルダーに直接移動します。
  
アイテム保持ポリシーを Exchange の場所に適用すると、タイマー ジョブが定期的に [回復可能なアイテム] フォルダー内のアイテムを評価します。 アイテムが少なくとも 1 つのアイテム保持ポリシーと一致しない場合、そのアイテムは [回復可能なアイテム] フォルダーから完全に削除されます (物理的な削除とも呼ばれます)。

タイマー ジョブの実行には最大 7 日かかる場合があり、Exchange の場所には少なくとも 10 MB が必要です。
  
ユーザーがメールボックスのアイテムのプロパティ (件名、本文、添付ファイル、送信者と受信者、メッセージの送受信日付など) を変更しようとすると、変更が確定される前に元のアイテムのコピーが [回復可能なアイテム] フォルダーに保存されます。 2 番目以降の変更ごとに、この操作が繰り返されます。 保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは完全に削除されます。

アイテム保持ポリシーがメールボックスまたはパブリック フォルダーに割り当てられた後のコンテンツのパスは、保持設定が保持および削除、保持のみ、あるいは削除のみのどれであるかによって異なります。

保持設定が保持および削除の場合

![メールおよびパブリック フォルダーの保持フローの図](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **保持期間中、ユーザーがアイテムを変更または完全に削除した場合** (この操作は Shift キーと Delete キーを押すか、[削除済みアイテム] から削除して行います): アイテムは [回復可能なアイテム] フォルダーに移動 (編集する場合はコピー) されます。 ここで、タイマー ジョブが定期的に実行され、アイテム保持ポリシーの有効期間が過ぎたアイテムを特定します。このようなアイテムは、保持期間の最終日から 14 日以内に完全に削除されます。 既定の設定は 14 日間ですが、最長 30 日間まで設定できます。

2. 保存期間中に**アイテムが変更または削除されない場合**: メールボックス内のすべてのフォルダーで同じプロセスが定期的に実行され、保持期間が終了したアイテムを識別します。これらのアイテムは保持期間の終了後 14 日以内に完全に削除されます。 既定の設定は 14 日間ですが、最長 30 日間まで設定できます。 

保持設定が保持のみ、または削除のみの場合、コンテンツ パスは保持か削除かで異なります。

### <a name="content-paths-for-retain-only-retention-settings"></a>保持設定が保持のみのコンテンツ パス

1. 保持期間中に、**アイテムが変更または削除された場合**、元のアイテムのコピーが [回復可能なアイテム] フォルダーに作成され、保持期間の終了まで保持されます。保持期間が終了すると、[回復可能なアイテム] フォルダー内のコピーは、アイテムの有効期限が切れてから 14 日以内に完全に削除されます。 

2. 保持期間中に**アイテムが変更または削除されてない場合**、保持期間の前後には何も起こりません。アイテムは、元の場所に残ります。

### <a name="content-paths-for-delete-only-retention-settings"></a>保持設定が削除のみのコンテンツ パス

1. 設定した期間中に**アイテムが削除されない場合**: アイテム保持ポリシーで構成された期間の最後に、アイテムは [回復可能なアイテム] フォルダーに移動されます。 

2. 設定した期間中に**アイテムが削除された場合**: アイテムはすぐに [回復可能なアイテム] フォルダーに移動されます。 ユーザーが [回復可能なアイテム] フォルダーからアイテムを削除するかフォルダーを空にすると、そのアイテムは完全に削除されます。 それ以外の場合、14 日が経過すると、アイテムは [回復可能なアイテム] フォルダーから完全に削除されます。 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>アイテム保持ポリシーから特定の種類の Exchange アイテムを除外する

保持設定が保持のみの場合、PowerShell を使用して、アイテム保持ポリシーから特定の種類の Exchange アイテムを除外することができます。 たとえば、メールボックスでボイスメール メッセージ、IM 会話、その他の Skype for Business Online のコンテンツを除外できます。 予定表、メモ、タスク アイテムを除外することもできます。 この機能は、PowerShell を使用した場合にのみ使用できます。Microsoft 365 コンプライアンス センターのウィザードを使用してアイテム保持ポリシーを作成する場合は使用できません。
  
アイテム保持ポリシーで選択した Exchange アイテムの種類を除外するには、`ExcludedItemClasses` パラメーターを [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) および [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule) コマンドレットで使用します。

アイテム保持ポリシーのコマンドレットを使用するには、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)する必要があります。

## <a name="when-a-user-leaves-the-organization"></a>ユーザーが組織を離れる場合 

ユーザーが組織を離れるときに、ユーザーのメールボックスがアイテム保持ポリシーに含まれていると、ユーザーの Microsoft 365 アカウントが削除されるときにメールボックスは非アクティブなメールボックスになります。 非アクティブなメールボックスのコンテンツは、メールボックスが非アクティブになる前に配置されたアイテム保持ポリシーがあれば、引き続きその適用対象となり、電子情報開示の検索が可能です。 詳細については、「[Exchange Online の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a>Exchange のアイテム保持ポリシーを構成する方法

「[アイテム保持ポリシーの作成と構成](create-retention-policies.md)」の手順に従い、ウィザードの [**場所の選択**] ページで、次のオプションのいずれかを選択します。

- **Exchange メール、パブリック フォルダー、Office 365 グループ、OneDrive および SharePoint ドキュメントのコンテンツにのみポリシーを適用する**

- [**特定の場所を選択する**] > [**Exchange メール**]、[**Exchange パブリック フォルダー**] と ［**Office 365 グループ**］。

Microsoft 365 グループには Exchange メールボックスがありますが、**Exchange メール**の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。 これらのメールボックスのコンテンツを保持するには、**Office 365 グループ**の場所を選択します。
