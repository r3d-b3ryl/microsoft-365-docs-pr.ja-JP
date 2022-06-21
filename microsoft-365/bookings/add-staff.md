---
title: Bookings にスタッフを追加する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: このページを使用して、スタッフリストを作成し、名前、電話番号、メール アドレスなどのスタッフ メンバーの詳細を管理します。
ms.openlocfilehash: b9acf72e9026b230702ed4cad232a92842b51028
ms.sourcegitcommit: af2b570e76e074bbef98b665b5f9a731350eda58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66185151"
---
# <a name="add-staff-to-bookings"></a>Bookings にスタッフを追加する

Bookings の [スタッフ] ページでは、スタッフリストを作成し、名前、電話番号、メール アドレスなどのスタッフ メンバーの詳細を管理します。 また、ここから各スタッフの勤務時間を設定することもできます。

## <a name="before-you-begin"></a>はじめに

Bookings はMicrosoft 365の機能ですが、すべてのスタッフメンバーがMicrosoft 365アカウントを持っている必要はありません。 すべてのスタッフ メンバーは、予約を受け取り、変更をスケジュールできるように、有効な電子メール アドレスを持っている必要があります。

## <a name="watch-add-your-staff-to-bookings"></a>ウォッチ: スタッフを Bookings に追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>手順

1. ホームページから予定表を選択します。

2. 左側のウィンドウのスタッフ オプションに移動し、[ **新しいスタッフの追加**] を選択します。

3. 組織内からスタッフを追加する場合は、[ **ユーザーの追加]** フィールドに名前を入力し、ドロップダウン メニューに表示されたら選択します。 その他のフィールドは自動的に設定されます。

    スタッフ メンバーが追加されたら、すべての Bookings 通信に表示される名前を編集するには、その名前の横にある **x** を選択し、[ **ユーザーの追加]** フィールドを編集します。 これは、Adele Vance を "Dr. Vance, MD" として一覧表示するなど、スタッフメンバーに特定のタイトルまたは名前を表示させる場合に役立ちます。

4. 組織外のスタッフを追加するには、メールやその他の情報を手動で入力します。

    > [!NOTE]
    > テナントの外部のスタッフは、空き時間情報を Bookings と共有できません。

5. 各スタッフ メンバーについて、チーム メンバー、スケジューラ、ビューアー、またはゲストのロールを選択します。
    - **チーム メンバー** は、自分の予定表で予約を管理し、予約メールボックスの空き時間を管理できます。 予定表で予約を追加または編集すると、スタッフとして割り当てられます。
    - **スケジューラは** 、予定表と顧客の詳細で予約を管理できます。 設定、スタッフ、およびサービスへの読み取り専用アクセス権があります。
    - **閲覧者** は予定表上のすべての予約を表示できますが、変更や削除はできません。 設定に対する読み取り専用アクセス権があります。
    - **ゲスト** は予約に割り当てることができますが、予約メールボックスを開くできません。

6. [ **割り当てられた予約が作成または変更されたときに、すべてのスタッフに電子メールで通知** する] を選択して、スタッフのメールを有効にします。 電子メールの例を次に示します。

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Bookings からの通知メール。":::

7. スタッフメンバー **の予定表** の空き時間情報が Bookings を通じて予約サービスの空き時間に影響を与える場合は、[Office 365予定表のイベント] を選択します。

    たとえば、水曜日の午後 3 時に予定されているチーム会議や個人的な予定があるスタッフメンバーの場合、Bookings では、そのスタッフ メンバーがそのタイム スロットで予約できないことが表示されます。 その時刻は、次の例に示すように、Bookings カレンダー ビューにビジー状態または仮の状態で表示されます。

    :::image type="content" source="media/bookings-busy-tentative-view-2.png" alt-text="Bookings カレンダーのビュー。":::

> [!IMPORTANT]
> ダブルブッキングを回避し、スタッフメンバーの可用性を最適化するために、この設定をオンのままにすることを非常に推奨します (既定ではオンになっています)。

8. [ **営業時間を使用する** ] を選択すると、スタッフ メンバーのすべての予約可能な時間が、[ビジネス情報] ページの [ **営業時間** ] セクションで設定した営業時間内のみに設定されます。

    このボックスの選択を解除すると、スタッフに、予約できる時間をさらに制限するカスタム時間を指定できます。 これは、スタッフメンバーが火曜日と水曜日にのみサイトに配置される場合や、1 種類の予定に朝を割り当て、午後を他の種類に割り当てられるシナリオに役立ちます。

    > [!NOTE]
    > Bookings Calendar では、最大 100 人のスタッフ メンバーがサポートされます。

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Bookings のスタッフとして追加せずに、Bookings ユーザーをスーパー ユーザーにする

ユーザーを顧客やクライアントが利用できるようにせずに、Bookings のスタッフ リストにユーザーを追加することもできます。 スーパー ユーザーにすると、予約メールボックスの管理者になります。 予約メールボックスの管理者は、予約メールボックスへのフル アクセスと送信アクセス許可を持つものとして定義されます。

> [!NOTE]
> これらの手順は、追加するユーザーが Bookings で **閲覧者** ロールをまだ割り当てられていない場合にのみ機能します。

1. [PowerShell を使用してMicrosoft 365するConnect](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. PowerShell を使用して、次のコマンドを使用してフル アクセスを割り当てます。

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. 次に、このコマンドを実行して、送信としてのアクセス許可を割り当てます。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Contoso の託児所予約メールボックスに Allie Bellew を追加する PowerShell コマンドの例を次に示します。

1. 最初に次のコマンドを実行します。

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. 次に、次のコマンドを実行します。

    ```powershell
    Add-RecipientPermission -Identity "daycare@contoso.com" -Trustee "Allie Bellew" -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** は管理者アクセス権を持つようになりましたが、Bookings では予約可能なスタッフとして表示されません。
