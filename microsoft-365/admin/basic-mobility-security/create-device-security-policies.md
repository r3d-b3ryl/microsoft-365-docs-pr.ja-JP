---
title: Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Basic Mobility and Security を使用して、組織情報を保護するデバイス ポリシーを作成します。
ms.openlocfilehash: 06d377e86913cbacd781241d75765e6b6cc63b8b
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775182"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する

Basic Mobility and Security を使用すると、承認されていないアクセスから組織の情報を保護するデバイス Microsoft 365作成できます。 ポリシーは、デバイスのユーザーが該当する Microsoft 365 ライセンスを持ち、デバイスを Basic Mobility and Security に登録している組織内の任意のモバイル デバイスに適用できます。

## <a name="before-you-begin"></a>開始する前に

> [!IMPORTANT]
> モバイル デバイス ポリシーを作成する前に、Basic Mobility and Security をアクティブ化してセットアップする必要があります。 詳細については、「Basic Mobility and Security の概要」を参照してください。

- Basic Mobility and Security がサポートするデバイス、モバイル デバイス アプリ、セキュリティ設定について説明します。 「Basic [Mobility and Security の機能」を参照してください](capabilities.md)。
- ポリシーを展開するユーザー Microsoft 365を含むセキュリティ グループを作成し、ポリシーへのアクセスがブロックされるのを除外する可能性があるユーザー Microsoft 365。 組織に新しいポリシーを展開する前に、少ないユーザーに展開してポリシーをテストすることをお勧めします。 自分またはポリシーをテストできるユーザーの数が少ないMicrosoft 365グループを作成して使用できます。 セキュリティ グループの詳細については、「セキュリティ グループの [作成、編集、または削除」を参照してください](../email/create-edit-or-delete-a-security-group.md)。
- 基本モビリティ ポリシーとセキュリティ ポリシーを Microsoft 365展開するには、グローバル管理者Microsoft 365必要があります。詳細については、「Security [&アクセス許可」を参照してください](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。
- ポリシーを展開する前に、Basic Mobility and Security にデバイスを登録する場合の潜在的な影響を組織に知らせて下さい。 ポリシーの設定方法に応じて、準拠しないデバイスが Microsoft 365 やデータ (登録済みデバイスにインストールされているアプリケーション、写真、個人情報など) へのアクセスをブロックし、データを削除できます。

> [!NOTE]
> Microsoft 365 Business Standard の基本モビリティとセキュリティで作成されたポリシーとアクセス ルールは、Exchange ActiveSync 管理センターで作成された Exchange ActiveSync Exchange モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。 デバイスが Basic Mobility and Security for Microsoft 365 Business Standard に登録されると、Exchange ActiveSync に適用されたモバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。 詳細については、「Exchange ActiveSync」の[Exchange ActiveSyncをExchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>手順 1: デバイス ポリシーを作成し、テスト グループに展開する

開始する前に、Basic Mobility and Security をアクティブ化してセットアップしてください。 手順については [、「Basic Mobility and Security の概要」を参照してください](overview.md)。

1. ブラウザーから、と入力します <https://protection.office.com/devicev2> 。

2. [**ポリシーの作成**] を選択します。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="モビリティポリシーとセキュリティポリシーの基本設定。":::

3. [ポリシー **設定] ページ** で、組織内のモバイル デバイスに適用する要件を指定します。

4. **メール プロファイルの管理** を要求する : 有効にすると、Basic Mobility と Security によって管理される電子メール プロファイルを持つデバイスは準拠していないと見なされます。 デバイスが正しくターゲットに設定されていない場合、またはユーザーがデバイスで電子メール アカウントを手動で設定した場合、デバイスに管理されたメール プロファイルを設定できません。 [無効] ( **既定) のままに** した場合、この設定はコンプライアンスまたは非準拠の評価を受け取らない。 このオプションを選択した場合にユーザーが準拠する方法については、「既存のメール アカウントが見つかりました」 [を参照してください](/intune-user-help/existing-company-email-account-found)。

5. [この **ポリシーを今すぐ適用しますか?** ] ページで、このポリシーを適用するグループを選択します。

6. [この **ポリシーの作成] を選択します**。

ポリシーは、次にモバイル デバイスを使用してユーザーにサインインする場合にポリシーが適用Microsoft 365デバイスにプッシュされます。 ユーザーが以前にモバイル デバイスにポリシーを適用したことがない場合、ポリシーを展開した後、基本モビリティとセキュリティを登録およびアクティブ化する手順を含む通知がデバイスに届きます。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。 Intune Service がホストする Basic Mobility and Security への登録が完了するまでは、電子メール、OneDrive、その他のサービスへのアクセスが制限されます。 アプリを使用して登録をIntune ポータル サイト、サービスを使用し、ポリシーがデバイスに適用されます。

## <a name="step-2-verify-that-your-policy-works"></a>手順 2: ポリシーが動作することを確認する

デバイス ポリシーを作成した後、組織に展開する前に、ポリシーが期待した通り動作します。

1. ブラウザーから、と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. [管理対象 **デバイスの一覧を表示する] を選択します**。
3. ポリシーが適用されているユーザー デバイスの状態を確認します。 デバイスの **状態** を管理する **必要があります。**
4. デバイスを選択した後、[出荷時のリセット] または [管理] ボタンから会社データを削除] をクリックして、デバイスで完全または選択的なワイプを実行することもできます。  手順については、「モバイル デバイスをワイプする」を参照Microsoft 365。

## <a name="step-3-deploy-a-policy-to-your-organization"></a>手順 3: 組織にポリシーを展開する

デバイス ポリシーを作成し、正常に動作する確認が完了したら、組織に展開します。

1. ブラウザーの種類: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) です。
2. 展開するポリシーを選択し、[適用するグループ] の横にある **[****編集] を選択します。**
3. 追加するグループを検索し、[選択] を **クリックします**。
4. [閉 **じる] と [****設定の変更] を選択します。**
5. [閉 **じる] と [****ポリシーの編集] を選択します。**

ポリシーは、次にモバイル デバイスからユーザーにサインインする場合にポリシーが適用Microsoft 365モバイル デバイスにプッシュされます。 ユーザーがモバイル デバイスにポリシーを適用していない場合は、デバイスに基本モビリティとセキュリティの登録とライセンス認証を行う手順を示す通知が届きます。 登録が完了すると、ポリシーがデバイスに適用されます。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>手順 4: サポートされていないデバイスの電子メール アクセスをブロックする

組織情報をセキュリティで保護するには、Basic Mobility and Security でサポートされていないモバイル デバイスMicrosoft 365メールへのアプリ アクセスをブロックする必要があります。 サポートされているデバイスの一覧については、「サポートされている [デバイス」を参照してください](../../admin/basic-mobility-security/capabilities.md)。

**アプリへのアクセスをブロックするには、次の方法を実行します。**

1. ブラウザーから、と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。
2. [組織 **全体のデバイス アクセス設定の管理] を選択します**。
3. サポートされていないデバイスをブロックするには、[デバイスが Basic Mobility and Security for Microsoft 365でサポートされていない場合] で [ブロック] を **選択し、[** 保存] を **選択します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Basic Mobility and Security block access option.":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>手順 5: 条件付きアクセスチェックから除外するセキュリティ グループを選択する

一部のユーザーをモバイル デバイスの条件付きアクセス チェックから除外し、それらのユーザーに対して 1 つ以上のセキュリティ グループを作成した場合は、ここにセキュリティ グループを追加します。 これらのグループのユーザーには、サポートされているモバイル デバイスに対してポリシーが適用されません。 これは、組織で Basic Mobility and Security を使用する必要がなくなった場合に推奨されるオプションです。

1. ブラウザーから、と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. [組織 **全体のデバイス アクセス設定の管理] を選択します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basic Mobility and Security は、ポリシー オプションを作成します。":::

3. [**追加]** を選択して、アクセスをブロックするユーザーを含むセキュリティ グループを追加Microsoft 365。 ユーザーがこのリストに追加された場合、サポートされていないデバイスを使用Microsoft 365メールにアクセスできます。

4. [グループの選択] パネルで使用する **セキュリティ グループを選択** します。

5. 名前を選択し、[保存の追加 **] を**  >  **クリックします**。

6. [組織全体 **のデバイス アクセス設定] パネルで、[** 保存] を **選択します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Basic Mobility and Security allow access option.":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>セキュリティ ポリシーが異なるデバイスの種類に与える影響は何ですか?

ユーザー デバイスにポリシーを適用すると、各デバイスへの影響はデバイスの種類によって多少異なります。 ポリシーが異なるデバイスに与える影響の例については、次の表を参照してください。

|**セキュリティ ポリシー**|**Android 4 以降**|**Samsung KNOX**|**iOS 6 以降**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求|いいえ|はい|はい|iOS 暗号化バックアップが必要です。|
|クラウド バックアップの禁止|はい|はい|はい|Android の Google バックアップをブロックする (灰色表示)、iOS のクラウド バックアップ。|
|ドキュメントの同期の禁止|いいえ|いいえ|はい|iOS: クラウド内のドキュメントをブロックします。|
|写真の同期の禁止 |いいえ|いいえ|はい|iOS (ネイティブ): フォト ストリームをブロックします。|
|画面キャプチャの禁止 |いいえ|はい|はい|試行時にブロックされます。|
|ビデオ会議をブロックする |いいえ|いいえ|はい|FaceTime は iOS でブロックされ、その他Skypeブロックされません。|
|診断データの送信をブロックする |いいえ|はい|はい|Android での Google クラッシュ レポートの送信をブロックします。|
|アプリ ストアへのアクセスをブロックする |いいえ|はい|はい|Android のホーム ページにアプリ ストア のアイコンが表示されません。アプリ Windows iOS では無効になっています。|
|アプリ ストアのパスワードを要求する |いいえ|いいえ|はい|iOS: iTunes の購入に必要なパスワード。|
|リムーバブル 記憶域への接続をブロックする |いいえ|はい|該当なし|Android: SD カードが設定で灰色表示されWindowsユーザーに通知する場合、インストールされているアプリは使用できません|
|Bluetooth 接続の禁止 |メモを見る|メモを見る|はい|Android の設定として BlueTooth を無効にできない。 代わりに、BlueTooth が必要なすべてのトランザクション (Advanced Audio Distribution、Audio/Video Remote Control、ハンズフリー デバイス、ヘッドセット、電話 ブック アクセス、シリアル ポート) を無効にします。 これらのメッセージが使用されている場合は、ページの下部に小さなトースト メッセージが表示されます。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>ポリシーを削除するか、ポリシーからユーザーを削除するとどうなるか。

ポリシーを削除するか、ポリシーが展開されたグループからユーザーを削除すると、ポリシー設定、Microsoft 365 メール プロファイル、キャッシュされた電子メールがユーザーのデバイスから削除される可能性があります。 次の表を参照して、さまざまなデバイスの種類に対して削除される機能を確認します。

|**削除された情報**|**iOS 6 以降**|**Android 4 以降 (Samsung KNOX を含む)**|
|:-----|:-----|:-----|
|管理されたメール プロファイル<sup>1</sup>|はい|いいえ|
|クラウド バックアップの禁止|はい|いいえ|

<sup>1</sup> [メール プロファイルを管理する]オプションが選択されたポリシーが展開されている場合、そのプロファイルの管理されたメール プロファイルとキャッシュされたメールは、ユーザー デバイスから削除されます。

ポリシーは、デバイスが Basic Mobility and Security で次回にログインする場合にポリシーが適用される各ユーザーのモバイル デバイスから削除されます。 これらのユーザー デバイスに適用される新しいポリシーを展開すると、Basic Mobility and Security に再登録するように求めるメッセージが表示されます。

デバイスを完全にワイプするか、デバイスから組織情報を選択的にワイプすることもできます。 詳細については、「Basic [Mobility and Security でモバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。

## <a name="related-content"></a>関連コンテンツ

[基本モビリティとセキュリティの概要](overview.md) (記事)\
[基本モビリティとセキュリティの機能](capabilities.md) (記事)