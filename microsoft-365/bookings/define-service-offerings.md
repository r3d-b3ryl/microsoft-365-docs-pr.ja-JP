---
title: Bookings でサービス提供を定義する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: サービス名、説明、場所、期間、価格などのサービス提供情報を入力する手順。 また、サービスを提供する資格がある従業員にタグを付けることもできます。
ms.openlocfilehash: 5b9720492429a6a46be8f2701315ccd5b92e1bf6
ms.sourcegitcommit: c41e3f48451e2d7b45901faee21b1e1d19a16688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2021
ms.locfileid: "58823879"
---
# <a name="define-your-service-offerings-in-bookings"></a>Bookings でサービス提供を定義する

Microsoft Bookings でサービス提供を定義する場合は、サービス名、説明、場所 (対人会議またはオンライン会議の開催を選択)、期間、顧客とスタッフへの既定のリマインダー、サービスに関する内部メモ、価格設定を設定します。 また、サービスを提供する資格がある従業員にタグを付けることもできます。 その後、顧客がビジネス Web サイトに来て予定を予約すると、利用可能な予定の種類、サービスを提供するユーザーの選択、およびサービスのコストを正確に確認できます。

また、ユーザーが予約ページからサービスを予約するときに送信するメールの確認とリマインダーに、カスタマイズされた情報と URL を追加することもできます。

## <a name="create-the-service-details"></a>サービスの詳細情報を作成する

1. [Microsoft 365] で[アプリ 起動ツール] を選択し、[予約]**を選択します**。

2. [サービスの管理  ->  [設定] ページに移動し、[](https://outlook.office.com/bookings/settings/services)新しいサービスの **追加] を選択します**。

3. [基本の **詳細] ページ** で、選択内容を追加します。

**サービス名**: サービスの名前を入力します。 これは、[予定表] ページのドロップダウン メニューに表示される名前です。 この名前は、[予定表] ページに予定を手動で追加すると表示され、[セルフサービス] ページにタイルとして表示されます。

**説明**: ユーザーがセルフサービス ページの情報アイコンをクリックすると、入力した説明が表示されます。

**既定の** 場所: この場所は、スタッフと顧客の両方の確認メールとリマインダー メールに表示される場所であり、予約用に作成された予定表イベントに表示されます。

**オンライン会議の追加**: この設定は、スタッフ メンバーの既定のクライアントとして構成する予定に応じて、Teams または Skype を介して、各予定のオンライン会議を有効または無効にします。

    - 有効:

        - 予約に固有の Teams または Skype 会議へのリンクが、スタッフと顧客の予定表の両方の予定表イベントにダイヤルイン情報と共に追加されます。
        - 会議に参加するリンクは、次の例に示すように、すべての確認メールとリマインダー メールに追加されます。

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Bookings で会議に参加Teamsリンクの例。":::

        > [!NOTE]
        > Teams会議は、Teams モバイル アプリ、Teams デスクトップ アプリ、Web ブラウザー、または電話ダイヤルインを介して参加できます。 仮想予定の予約をTeams最適なエクスペリエンスを得る上で、テナントの既定のオンライン会議サービスとして会議を有効にすることを強く推奨します。

    - 無効:
        - 予定には会議オプションが含まれるのではなく、オンライン会議の追加が有効になっているときに表示される会議関連のすべてのフィールドは表示されません。

**期間**: これは、すべての会議の予約期間です。 時刻は、予約中に選択された開始時刻からブロックされます。 スタッフの予定表では、完全な予定時間がブロックされます。

**バッファー時間**: この設定を有効にすると、予定が予約されるごとにスタッフの予定表に余分な時間を追加できます。

    The time will be blocked on the staff’s calendar and impact free/busy information. This means if an appointment ends at 3:00 pm and 10 minutes of buffer time has been added to the end of the meeting, the staff’s calendar will show as busy and non-bookable until 3:10pm. This can be useful if your staff needs time before a meeting to prepare, such as a doctor reviewing a patient’s chart, or a financial advisor preparing relevant account information. It can also be useful after a meeting, such as when someone needs time to travel to another location.

**価格が設定されていない**  [価格] ページに表示される価格オプションSelf-Serviceします。 [ **価格が設定されていない** ] が選択されている場合、価格またはコストまたは価格への参照は表示されません。

**メモ** このフィールドは、予約されたスタッフの予約イベント、および Bookings Web アプリの [予定表] タブに表示されるイベントに表示されます。

**イベントごとの最大出席者数** この設定では、複数のユーザーが同じ予定時間と同じスタッフ (フィットネス クラスなど) を予約する機能を必要とするサービスを作成できます。 選択したサービス、スタッフ、および時間の予定タイム スロットは、ユーザーが指定した出席者の最大数に達するまで予約できます。 現在の予定の容量と出席者は、Bookings Web アプリの [予定表] タブで表示できます。

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Example of setting maximum attendees in Bookings":::

**顧客が予約** を管理する : この設定は、予約が Bookings Web アプリの [予定表] タブで予約されている場合に、顧客が予約を変更またはキャンセルできるかどうかを決定します。

    - 有効:

        [ **予約の管理]** ボタンが顧客確認メールに表示されます。 このボタンを顧客が選択すると、次の 3 つのオプションが表示されます。
        - **再スケジュール** このオプションを選択すると、ユーザーはサービス固有の Self-Service ページに移動し、元の予約から同じサービスと同じスタッフ メンバーの新しい日時を選択できます。 既定では、元のスタッフ メンバーが再スケジュールされた予約に接続されている場合でも、スタッフ メンバーを変更することもできます。
        - **予約のキャンセル** これにより、予約が取り消され、スタッフの予定表から削除されます。
        - **新しい予約** このオプションを使用すると、新しいSelf-Serviceスケジュールを設定するために、すべてのサービスとスタッフが一覧表示されたページにユーザーが移動します。

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="[予約] の [予約の管理] ボタン。":::

        この設定は、ユーザーがページにアクセスする場合にのみ有効にSelf-Service勧めします。

    - 無効:

        ユーザーは、Bookings Web アプリの [予定表] タブから予約を行う際に予約を再スケジュールまたはキャンセルする機能を持つ必要はありません。 ただし、[予約] ページSelf-Service、この設定が無効になっている場合でも、[予約の管理] ボタンとそのすべてのオプションが表示されます。

        ページへのアクセスを制限する場合は、この設定をSelf-Service勧めします。 さらに、確認メールやリマインダーメールにテキストを追加し、その他の方法で予約を変更する方法 (オフィスに電話をしたり、ヘルプ デスクにメールを送るなど) を行う方法を顧客に伝えます。

4. [空 **き時間情報のオプション**] ページで、スケジュール ポリシーとスタッフの空き時間情報について、[予約] ページで選択したオプションを確認できます。 詳細については、「スケジュール ポリシーの [設定」を参照してください](set-scheduling-policies.md)。

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Bookings で最大出席者数を設定する例。":::

10. **既定の価格**  これは、ページに表示される価格Self-Serviceです。 [ **価格が設定されていない** ] が選択されている場合、価格またはコストまたは価格への参照は表示されません。

11. **メモ** このフィールドは、予約されたスタッフの予約イベント、および Bookings Web アプリの [予定表] タブに表示されるイベントに表示されます。

6. **ユーザー設定フィールド** は、特定の予定が予約される度に必要な情報を収集するときに役立ちます。 例としては、診療所訪問前の保険会社、ローン相談のローンの種類、学術的なアドバイスのための主要な研究、または候補者の面接の申請者 ID が含まれます。 これらのフィールドは、顧客が自分とスタッフと一緒に予定を予約するときに、[予約] ページに表示されます。

    - 顧客の電子メール、電話番号、住所、メモは取り外し不可のフィールドですが、各フィールドの横にある[必須] の選択を解除すると、それらをオプションにできます。

7. [アラーム **と確認] ページ** で、送信するリマインダーと通知を設定できます。 アラームと通知は、予定の前に指定した時刻に、顧客、スタッフ メンバー、または両方に送信されます。 好みに応じて、予定ごとに複数のメッセージを作成できます。

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="A confirmation email from Bookings.":::

    - 再スケジュールに関する情報や、顧客が予定に持ち込む必要があるものなど、ここに必要な追加のテキストを含めできます。 [電子メールの確認の追加情報] フィールドに表示される、元の確認メールに追加されたカスタマイズされたテキスト **の例を次に示** します。

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Bookings メールの追加情報。":::

8. **顧客のテキスト メッセージ通知を有効にする** 選択されている場合、SMS メッセージは顧客に送信されますが、ユーザーがオプトインした場合にのみ送信されます。

    - 手動の予約とページの [オプトイン] ボックスSelf-Serviceします。

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Bookings のオプトイン ボックス。":::

    - テキスト メッセージ通知は次のようになります (現在、SMS 通知は北米でのみ利用可能です)。

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Bookings からのテキスト通知。":::

9. 既定 **では、既定のスケジュール オプション** がオンになっています。 ユーザーが特定のスタッフ メンバーを予約する方法をカスタマイズする場合は、トグルをオフにします。

10. **発行オプション** このサービスを Self-Service ページで予約可能にするか、Bookings Web アプリの [予定表] タブでのみ予約可能にするかどうかを選択します。
