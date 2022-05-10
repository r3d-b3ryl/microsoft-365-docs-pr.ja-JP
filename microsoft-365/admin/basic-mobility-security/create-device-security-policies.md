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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティを使用して、組織の情報を保護するデバイス ポリシーを作成します。
ms.openlocfilehash: d4e693d27ea71cdd18c9ea668a2102e0ce061b8d
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63400449"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する

Basic Mobility and Security を使用して、Microsoft 365に関する組織情報を不正アクセスから保護するのに役立つデバイス ポリシーを作成できます。 デバイスのユーザーが適用可能なMicrosoft 365 ライセンスを持ち、デバイスを Basic Mobility and Security に登録している組織内の任意のモバイル デバイスにポリシーを適用できます。

## <a name="before-you-begin"></a>はじめに

> [!IMPORTANT]
> モバイル デバイス ポリシーを作成する前に、基本的なモビリティとセキュリティをアクティブ化して設定する必要があります。 詳細については、「基本的なモビリティとセキュリティの概要」を参照してください。

- Basic Mobility と Security でサポートされているデバイス、モバイル デバイス アプリ、セキュリティ設定について説明します。 [基本的なモビリティとセキュリティの機能に関する説明を参照してください](capabilities.md)。
- ポリシーを展開するMicrosoft 365ユーザーと、Microsoft 365へのアクセスをブロックされないように除外する可能性があるユーザーを含むセキュリティ グループを作成します。 組織に新しいポリシーを展開する前に、少数のユーザーにポリシーを展開してポリシーをテストすることをお勧めします。 自分だけを含むセキュリティ グループ、またはポリシーをテストできる少数のMicrosoft 365ユーザーを含むセキュリティ グループを作成して使用できます。 セキュリティ グループの詳細については、「セキュリティ グループの [作成、編集、または削除](../email/create-edit-or-delete-a-security-group.md)」を参照してください。
- Microsoft 365で基本的なモビリティポリシーとセキュリティ ポリシーを作成して展開するには、Microsoft 365グローバル管理者である必要があります。詳細については、「[セキュリティ & コンプライアンス センターのアクセス許可」を](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)参照してください。
- ポリシーを展開する前に、基本的なモビリティとセキュリティにデバイスを登録することによる潜在的な影響を組織に知らせます。 ポリシーの設定方法に応じて、非準拠デバイスは、登録済みデバイスにインストールされているアプリケーション、写真、個人情報を含むMicrosoft 365とデータへのアクセスをブロックでき、データを削除できます。

> [!NOTE]
> Microsoft 365 Business Standardの基本的なモビリティとセキュリティで作成されたポリシーとアクセス規則は、Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>で作成Exchange ActiveSyncモバイル デバイス メールボックス ポリシーとデバイス アクセス規則をオーバーライドします。 デバイスが Basic Mobility and Security for Microsoft 365 Business Standard に登録されると、デバイスに適用されたモバイル デバイス メールボックス ポリシーまたはデバイス アクセス規則Exchange ActiveSyncは無視されます。 Exchange ActiveSyncの詳細については、Exchange Online[のExchange ActiveSyncを](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)参照してください。

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>手順 1: デバイス ポリシーを作成し、テスト グループに展開する

開始する前に、基本的なモビリティとセキュリティをアクティブ化して設定していることを確認します。 手順については、「 [基本的なモビリティとセキュリティの概要」](overview.md)を参照してください。

1. ブラウザーから「.」と入力します <https://protection.office.com/devicev2>。

2. [**ポリシーの作成**] を選択します。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なモビリティとセキュリティのポリシー設定。":::

3. [ **ポリシー設定]** ページで、組織内のモバイル デバイスに適用する要件を指定します。

4. **電子メール プロファイルを管理する必要がある**: 有効にすると、Basic Mobility と Security によって管理されている電子メール プロファイルを持たないデバイスは準拠していないと見なされます。 デバイスが正しくターゲット設定されていない場合、またはユーザーがデバイスに電子メール アカウントを手動で設定した場合、デバイスは管理対象の電子メール プロファイルを持つことができません。 **[無効]** のままにした場合 (既定)、この設定はコンプライアンスまたは非対応として評価されません。 このオプションを選択したときにユーザーが準拠する方法については、「 [既存のメール アカウントが見つかりました](/intune-user-help/existing-company-email-account-found)」を参照してください。

5. [ **このポリシーを今すぐ適用しますか]** ページで、このポリシーを適用するグループを選択します。

6. [ **このポリシーの作成**] を選択します。

ポリシーは、次にモバイル デバイスを使用してMicrosoft 365にサインインする際にポリシーが適用される各ユーザーのデバイスにプッシュされます。 ユーザーが以前にモバイル デバイスに適用されたポリシーを持っていない場合は、ポリシーを展開した後に、Basic Mobility と Security を登録してアクティブ化する手順を含む通知がデバイスに表示されます。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。 Intune サービスによってホストされる Basic Mobility and Security への登録が完了するまでは、電子メール、OneDrive、およびその他のサービスへのアクセスが制限されます。 Intune ポータル サイト アプリを使用して登録を完了すると、サービスを使用でき、ポリシーがデバイスに適用されます。

## <a name="step-2-verify-that-your-policy-works"></a>手順 2: ポリシーが機能することを確認する

デバイス ポリシーを作成したら、組織に展開する前に、ポリシーが想定どおりに機能することを確認します。

1. ブラウザーから「.」と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2)。
2. [ **管理対象デバイスの一覧を表示する**] を選択します。
3. ポリシーが適用されているユーザー デバイスの状態を確認します。 デバイスの **状態** を管理する必要があります **。**
4. デバイスを選択した後に[ **Factory reset** ]\(会社 **のデータ** を **管理** から削除\) ボタンをクリックして、デバイスの完全ワイプまたは選択的ワイプを実行することもできます。 手順については、「Microsoft 365でモバイル デバイスをワイプする」を参照してください。

## <a name="step-3-deploy-a-policy-to-your-organization"></a>手順 3: ポリシーを組織に展開する

デバイス ポリシーを作成し、それが期待どおりに動作することを確認したら、それを組織に展開します。

1. ブラウザーの種類から: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).
2. 展開するポリシーを選択し、**適用先のグループ** の横にある **[編集]** を選択します。
3. 追加するグループを検索し、[ **選択**] をクリックします。
4. [ **閉じる** ] と **[変更] の設定を選択します。**
5. [ **閉じる** ] と **[ポリシーの編集] を選択します。**

ポリシーは、次回モバイル デバイスからMicrosoft 365にサインインする際にポリシーが適用される各ユーザーのモバイル デバイスにプッシュされます。 ユーザーがモバイル デバイスにポリシーを適用していない場合は、デバイスに通知を受け取り、Basic Mobility and Security に登録してアクティブ化する手順を示します。 登録が完了すると、ポリシーがデバイスに適用されます。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。

## <a name="step-4-block-email-access-for-unsupported-devices"></a>手順 4: サポートされていないデバイスの電子メール アクセスをブロックする

組織の情報をセキュリティで保護するために、Basic Mobility and Security でサポートされていないモバイル デバイスのMicrosoft 365メールへのアプリ アクセスをブロックする必要があります。 サポートされているデバイスの一覧については、「 [サポートされているデバイス](../../admin/basic-mobility-security/capabilities.md)」を参照してください。

**アプリへのアクセスをブロックするには:**

1. ブラウザーから「.」と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2)。
2. [ **組織全体のデバイス アクセス設定の管理] を選択します**。
3. サポートされていないデバイスをブロックするには、[**デバイスが Basic Mobility and Security for Microsoft 365でサポートされていない場合**] で **[ブロック**] を選択し、[保存] を選択 **します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="基本的なモビリティとセキュリティ ブロックのアクセス オプション。":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>手順 5: 条件付きアクセス チェックから除外するセキュリティ グループを選択する

一部のユーザーをモバイル デバイスの条件付きアクセス チェックから除外し、それらのユーザーに対して 1 つ以上のセキュリティ グループを作成した場合は、ここにセキュリティ グループを追加します。 これらのグループのユーザーには、サポートされているモバイル デバイスに適用されるポリシーはありません。 これは、組織で Basic Mobility と Security を使用する必要がなくなった場合に推奨されるオプションです。

1. ブラウザーから「.」と入力します [https://protection.office.com/devicev2](https://protection.office.com/devicev2)。

2. [ **組織全体のデバイス アクセス設定の管理] を選択します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的なモビリティとセキュリティによってポリシー オプションが作成されます。":::

3. [**追加]** を選択して、Microsoft 365へのアクセスをブロックしないように除外するユーザーを含むセキュリティ グループを追加します。 ユーザーがこの一覧に追加されると、サポートされていないデバイスを使用しているときにMicrosoft 365電子メールにアクセスできます。

4. [グループの選択] パネルで、使用するセキュリティ **グループを選択** します。

5. 名前を選択し、**AddSave** >  を選択 **します**。

6. **組織全体のデバイス アクセス設定パネルで**、[保存] を選択 **します**。

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="基本的なモビリティとセキュリティは、アクセスを許可するオプションです。":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>さまざまなデバイスの種類に対するセキュリティ ポリシーの影響は何ですか?

ユーザー デバイスにポリシーを適用すると、各デバイスへの影響はデバイスの種類によって多少異なります。 さまざまなデバイスに対するポリシーの影響の例については、次の表を参照してください。

|**セキュリティ ポリシー**|**Android**|**Samsung KNOX**|**iOS**|**注**|
|:-----|:-----|:-----|:-----|:-----|
|暗号化されたバックアップを要求|いいえ|はい|はい|iOS 暗号化バックアップが必要です。|
|クラウド バックアップの禁止|はい|はい|はい|Android で Google バックアップをブロックする (淡色表示)、iOS でのクラウド バックアップ。|
|ドキュメントの同期の禁止|いいえ|いいえ|はい|iOS: クラウド内のドキュメントをブロックします。|
|写真の同期の禁止 |いいえ|いいえ|はい|iOS (ネイティブ): フォト ストリームをブロックします。|
|画面キャプチャの禁止 |いいえ|はい|はい|試行時にブロックされます。|
|ビデオ会議をブロックする |いいえ|いいえ|はい|FaceTime は iOS でブロックされ、Skypeや他のユーザーではブロックされません。|
|診断データの送信をブロックする |いいえ|はい|はい|Android での Google クラッシュ レポートの送信をブロックします。|
|アプリ ストアへのアクセスをブロックする |いいえ|はい|はい|Android ホーム ページでアプリ ストア アイコンが見つからない、Windowsで無効、iOS で見つかりません。|
|アプリ ストアのパスワードを要求する |いいえ|いいえ|はい|iOS: iTunes の購入に必要なパスワード。|
|リムーバブル ストレージへの接続をブロックする |いいえ|はい|該当なし|Android: SD カードは設定で淡色表示され、ユーザーに通知Windows、インストールされたアプリは使用できません|
|Bluetooth 接続の禁止 |メモを表示する|メモを表示する|はい|Android の設定として BlueTooth を無効にすることはできません。 代わりに、BlueTooth を必要とするすべてのトランザクション (Advanced Audio Distribution、Audio/Video Remote Control、ハンズフリー デバイス、ヘッドセット、電話 Book Access、シリアル ポート) を無効にします。 これらのメッセージのいずれかが使用されると、ページの下部に小さなトースト メッセージが表示されます。|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>ポリシーを削除するか、ポリシーからユーザーを削除するとどうなりますか?

ポリシーを削除するか、ポリシーが展開されたグループからユーザーを削除すると、ポリシー設定、Microsoft 365電子メール プロファイル、キャッシュされた電子メールがユーザーのデバイスから削除される可能性があります。 次の表を参照して、さまざまなデバイスの種類に対して削除される内容を確認します。

|**削除された内容**|**iOS**|**Android (Samsung KNOX を含む)**|
|:-----|:-----|:-----|
|Managed email <sup>profiles1</sup>|はい|いいえ|
|クラウド バックアップの禁止|はい|いいえ|

<sup>1</sup> [ **電子メール プロファイルが管理** されている] オプションを選択してポリシーが展開された場合、そのプロファイル内のマネージド 電子メール プロファイルとキャッシュされた電子メールがユーザー デバイスから削除されます。

ポリシーは、デバイスが次回 Basic Mobility and Security でチェックインする際に適用される各ユーザーのモバイル デバイスから削除されます。 これらのユーザー デバイスに適用される新しいポリシーを展開すると、基本モビリティとセキュリティに再登録するように求められます。

デバイスを完全にワイプすることも、デバイスから組織の情報を選択的にワイプすることもできます。 詳細については、「 [Basic Mobility and Security でモバイル デバイスをワイプする](wipe-mobile-device.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[基本的なモビリティとセキュリティの概要](overview.md) (記事)\
[Basic Mobility and Security の機能](capabilities.md) (記事)