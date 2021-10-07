---
title: Bookings にスタッフを追加する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: このページを使用して、スタッフ リストを作成し、スタッフ メンバーの詳細 (名前、電話番号、電子メール アドレスなど) を管理します。
ms.openlocfilehash: ea9025edd20289aa404471f6c1d245e7bf5c7d4e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202155"
---
# <a name="add-staff-to-bookings"></a>Bookings にスタッフを追加する

Bookings の [スタッフ] ページでは、スタッフリストを作成し、スタッフ メンバーの詳細 (名前、電話番号、電子メール アドレスなど) を管理します。 また、ここから各スタッフの勤務時間を設定できます。

## <a name="before-you-begin"></a>はじめに

Bookings は、Microsoft 365の機能ですが、すべてのスタッフがアカウントを持つ必要Microsoft 365ではありません。 予約を受け取り、変更をスケジュールするには、すべてのスタッフが有効な電子メール アドレスを持っている必要があります。

## <a name="watch-add-your-staff-to-bookings"></a>ウォッチ: 予約にスタッフを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>手順

1. [スタッフの管理] [ページに移動し、[](https://outlook.office.com/bookings/staff) スタッフの追加 **] を選択します。**

2. [スタッフの **追加] ボタンを** 選択します。

3. 組織内からスタッフを追加する場合は、[ユーザーの追加]フィールドに名前を入力し、ドロップダウン メニューに表示されたら選択します。 他のフィールドは自動的に設定されます。

    スタッフ メンバーが追加されたら、すべての Bookings コミュニケーションに表示される名前を編集するには、そのメンバーの名前の横にある **x** を選択し、[ユーザーの追加] フィールド **を編集** します。 これは、Adele Vance を "Dr. Vance, MD" としてリストするなど、スタッフメンバーに特定のタイトルまたは名前を表示する場合に便利です。

4. 組織外からスタッフを追加するには、メールなどの情報を手動で入力します。

    > [!NOTE]
    > テナント外のスタッフは、空き時間情報を Bookings と共有できません。

5. 各スタッフ メンバーに対して、役割 (管理者、ビューアー、またはゲスト) を選択します。
    - **管理者は** 、すべての設定の編集、スタッフの追加と削除、予約の作成、編集、または削除を行います。
    - **閲覧** 者はカレンダー上のすべての予約を表示できますが、変更や削除は行えます。 設定への読み取り専用アクセス権があります。
    - **ゲスト** は予約に割り当てることができますが、予約メールボックスを開くことができません。

6. [ **割り当てられた予約が** 作成または変更された場合に、すべてのスタッフにメールで通知する] を選択して、スタッフのメールを有効にします。 電子メールの例を次に示します。

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Bookings からの通知メール。":::

7. スタッフ **メンバーの予定表Office 365空** き時間情報が Bookings を通じて予約サービスの可用性に影響を与える場合は、[スケジュールカレンダーのイベント] を選択します。

    たとえば、水曜日の午後 3 時にチーム会議または個人の予定がスタッフ メンバーにスケジュールされている場合、Bookings は、そのスタッフ メンバーが、そのタイム スロットで予約できないと表示されます。 この時間は、次の例に示すように、予約カレンダー ビューにビジーまたは暫定的に表示されます。

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Bookings カレンダーのビュー。":::

> [!IMPORTANT]
> ダブル予約を避け、スタッフ メンバーの可用性を最適化するために、この設定をオンのままにすることを強くお勧めします (既定では有効になっています)。

8. [**ビジネス情報]** ページの [営業時間] セクションで設定した営業時間内にのみ、スタッフメンバーのすべての予約可能な時間を設定するには、[営業時間を使用する] を選択します。

    このボックスの選択を解除すると、スタッフに予約できる時間をさらに制限するカスタム時間を指定できます。 これは、スタッフメンバーが火曜日と水曜日にしかサイトにいない場合や、1 種類の予定に対して朝を、その他の種類の午後に使用する場合に役立ちます。

    > [!NOTE]
    > スタッフ ページに追加した最初の 31 人のスタッフ メンバーだけが、サービスにスタッフ メンバーを割り当てるときに表示されます。

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Bookings ユーザーを、Bookings のスタッフとして追加せずにスーパー ユーザーにする

ユーザーを顧客またはクライアントが利用できない場合は、Bookings のスタッフ リストにユーザーを追加できます。 スーパー ユーザーになると、予約メールボックスの管理者になります。 予約メールボックスの管理者であることは、予約メールボックスに対するフル アクセスおよび送信権限を持つこととして定義されます。

> [!NOTE]
> これらの手順は、追加するユーザーに Bookings でビューアー ロールがまだ割り当てられていない場合にのみ機能します。

1. [Connect PowerShell をMicrosoft 365する方法を説明します](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

2. PowerShell を使用して、次のコマンドでフル アクセスを割り当てる。

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. 次に、このコマンドを実行して send-as アクセス許可を割り当てる。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Contoso のデケア予約メールボックスに Allie Bellew を追加する PowerShell コマンドの例を次に示します。

1. まず、次のコマンドを実行します。

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. 次に、次のコマンドを実行します。

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew は** 管理者アクセス権を持っていますが、Bookings では予約可能なスタッフとして表示されません。
