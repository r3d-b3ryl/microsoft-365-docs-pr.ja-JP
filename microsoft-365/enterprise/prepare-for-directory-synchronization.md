---
title: Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: ディレクトリ同期を使用してユーザーにMicrosoft 365準備する方法と、このメソッドを使用する長期的な利点について説明します。
ms.openlocfilehash: fc2fa76e61afeb0efeeef9fca7f66ac34ec83c77169551b859724b86b766c2c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53885137"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*

組織のハイブリッド ID とディレクトリ同期の利点は次のとおりです。

- 組織内の管理プログラムの削減
- 必要に応じてシングル サインオン シナリオを有効にする
- アカウントの変更を自動化するMicrosoft 365

ディレクトリ同期を使用する利点の詳細については、「ハイブリッド ID with [Azure Active Directory (Azure AD)」](/azure/active-directory/hybrid/whatis-hybrid-identity)および「ハイブリッド[ID」](plan-for-directory-synchronization.md)を参照Microsoft 365。

ただし、ディレクトリ同期では、Active Directory ドメイン サービス (AD DS) が最小エラーで Microsoft 365 サブスクリプションの Azure AD テナントと同期するように計画と準備が必要です。

最適な結果を得るには、次の手順に従います。

## <a name="1-directory-cleanup-tasks"></a>1. ディレクトリのクリーンアップ タスク

Ds を Azure ADテナントAD同期する前に、DS をクリーンアップするADがあります。

> [!IMPORTANT]
> 同期する前に DS クリーンアップAD実行しない場合、展開プロセスに大きな悪影響を及ぼす可能性があります。 ディレクトリ同期、エラーの特定、および再同期のサイクルを実行するには、数日または数週間かかる場合があります。

DS でADライセンスが割り当てられる各ユーザー アカウントについて、次のクリーンアップ タスクをMicrosoft 365します。

1. proxyAddresses 属性で有効で一意の **電子メール アドレスを確認** します。

2. proxyAddresses 属性の重複 **する値を削除** します。

3. 可能であれば、ユーザーのユーザー オブジェクトの **userPrincipalName** 属性の有効で一意の値を **確認** します。 最適な同期エクスペリエンスを得る場合は、DS UPN ADと AZURE の同期が一致ADしてください。 ユーザーに **userPrincipalName** 属性の値が設定されていない場合、ユーザーオブジェクトには **sAMAccountName** 属性の有効で一意の値が含まれている必要があります。 **userPrincipalName 属性内の重複する値を削除** します。

4. グローバル アドレス一覧 (GAL) を最適に使用するには、DS ユーザー アカウントの次AD情報が正しいか確認します。

   - givenName
   - surname
   - displayName
   - 役職
   - 部署
   - 事業所
   - 事業所電話番号
   - 携帯電話番号
   - FAX 番号
   - 番地
   - 都市
   - 都道府県
   - 郵便番号
   - 国または地域

## <a name="2-directory-object-and-attribute-preparation"></a>2. ディレクトリ オブジェクトと属性の準備

DS とデバイス間のディレクトリ同期AD成功Microsoft 365 DS 属性を適切に準備ADする必要があります。 たとえば、特定の文字が特定の属性で使用され、特定の属性が特定の属性と同期Microsoft 365があります。 予期しない文字を使用すると、ディレクトリ同期は失敗しませんが、警告が返される可能性があります。 無効な文字を指定すると、ディレクトリ同期が失敗します。

また、一部の DS ユーザーが 1 つ以上の重複AD場合、ディレクトリ同期は失敗します。 各ユーザーは、一意の属性を持っている必要があります。

準備する必要がある属性を次に示します。

- **displayName**

  - 属性がユーザー オブジェクトに存在する場合、属性はユーザー オブジェクトと同期Microsoft 365。
  - この属性がユーザー オブジェクトに存在する場合は、その属性の値が必要です。 つまり、属性を空白にすることはできません。
  - 最大文字数: 256

- **givenName**

  - 属性がユーザー オブジェクトに存在する場合、属性は Microsoft 365 と同期されますが、Microsoft 365を必要としたり使用したりしません。
  - 最大文字数: 64

- **mail**

  - 属性値はディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 重複する値がある場合は、値を持つ最初のユーザーが同期されます。 後続のユーザーは、そのユーザーにMicrosoft 365。 両方のユーザーが Microsoft 365に表示するには、AD DS の値を変更するか、両方の値を変更するMicrosoft 365。

- **mailNickname** (Exchangeエイリアス)

  - 属性値はピリオド (.) で始めできません。
  - 属性値はディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 同期名のアンダースコア ("_") は、この属性の元の値に無効な文字が含まれているかどうかを示します。 この属性の詳細については、「alias 属性Exchange[参照してください](/powershell/module/exchange/set-mailbox)。
    >

- **proxyAddresses**

  - 複数値属性
  - 値あたりの最大文字数: 256
  - 属性値にはスペースを含めずに指定してください。
  - 属性値はディレクトリ内で一意である必要があります。
  - 無効な文字: \< \> ( ) ; , , [ ] "

    無効な文字は、型の区切り文字と ":"に続く文字に適用され、SMTP:User@contso.com が許可されますが、SMTP:user:M@contoso.com されません。

    > [!IMPORTANT]
    > すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。 重複アドレスまたは不要なアドレスが存在する場合は削除します。

- **sAMAccountName**

  - 最大文字数: 20
  - 属性値はディレクトリ内で一意である必要があります。
  - 無効な文字: [ \ " | 、 / : \< \> + = ; ? \* ']
  - ユーザーが無効な **sAMAccountName** 属性を持ち、有効な **userPrincipalName** 属性を持つ場合、ユーザー アカウントはユーザー アカウントにMicrosoft 365。
  - **sAMAccountName と** **userPrincipalName** の両方が無効な場合は、AD DS **userPrincipalName** 属性を更新する必要があります。

- **sn** (姓)

  - 属性がユーザー オブジェクトに存在する場合、属性は Microsoft 365 と同期されますが、Microsoft 365を必要としたり使用したりしません。

- **targetAddress**

    ユーザーに対して設定された **targetAddress** 属性 (SMTP:tom@contoso.com など) が、MICROSOFT 365 GAL に表示される必要があります。 サード パーティ製のメッセージング移行シナリオでは、DS のMicrosoft 365スキーマ拡張機能がADされます。 またMicrosoft 365スキーマ拡張機能は、DS のディレクトリ同期ツールを使用してMicrosoft 365オブジェクトを管理するために、他の有用な属性ADします。 たとえば、非表示のメールボックスまたは配布グループを管理するための **msExchHideFromAddressLists** 属性が追加されます。

  - 最大文字数: 256
  - 属性値にはスペースを含めずに指定してください。
  - 属性値はディレクトリ内で一意である必要があります。
  - 無効な文字: \ \< \> ( ) ; , [ ] "
  - すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。

- **userPrincipalName**

  - **userPrincipalName** 属性は、インターネット スタイルのサインイン形式で、ユーザー名の後に at 記号 (@) とドメイン名 (たとえば、user@contoso.com) を指定する必要があります。 すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。
  - **userPrincipalName 属性** の最大文字数は 113 です。 次のように、アット記号 (@) の前と後に特定の文字数を使用できます。
  - アット 記号の前にあるユーザー名の最大文字数 (@): 64
  - @記号 (@) に続くドメイン名の最大文字数: 48
  - 無効な文字: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - 使用できる文字: A ~ Z、a - z、0 ~ 9、' です。 - _ ! # ^ ~
  - umlauts、アクセント、チルドなど、二等分記号を持つ文字は無効な文字です。
  - @ 文字は、各 **userPrincipalName 値で必要** です。
  - @ 文字は、各 **userPrincipalName** 値の最初の文字にすることはできません。
  - ユーザー名は、ピリオド (.)、アンパサンド ( )、スペース、またはアット 記号 &amp; (@) で終了できません。
  - ユーザー名にスペースを含めることはできません。
  - Routable ドメインを使用する必要があります。たとえば、ローカル ドメインまたは内部ドメインは使用できません。
  - Unicode はアンダースコア文字に変換されます。
  - **userPrincipalName には** 、ディレクトリに重複する値を含めできません。

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. userPrincipalName 属性を準備する

Active Directory は、組織内のエンド ユーザーが **sAMAccountName** または **userPrincipalName** を使用してディレクトリにサインインするように設計されています。 同様に、エンド ユーザーは、自分のMicrosoft 365または学校アカウントのユーザー プリンシパル名 (UPN) を使用して、ユーザーにサインインできます。 ディレクトリ同期は、DS 内の同Azure Active Directory UPN を使用して、新しいユーザーを作成ADします。 UPN は電子メール アドレスのように書式設定されます。

このMicrosoft 365 UPN は、電子メール アドレスの生成に使用される既定の属性です。 **userPrincipalName** (AD DS および Azure AD) と **proxyAddresses** のプライマリ 電子メール アドレスを異なる値に設定するのは簡単です。 異なる値に設定すると、管理者とエンド ユーザーが混乱する可能性があります。

これらの属性を揃えて混乱を減らすのが最善の方法です。 Active Directory フェデレーション サービス (AD FS) 2.0 でのシングル サインオンの要件を満たすには、Azure Active Directory の UPN と AD DS が一致し、有効なドメイン名前空間を使用していることを確認する必要があります。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. DS に代替 UPN サフィックスをADする

ユーザーの会社の資格情報をユーザー環境に関連付ける代替 UPN サフィックスを追加するMicrosoft 365があります。 UPN サフィックスは、@ 文字の右側の UPN の一部です。 シングル サインオンに使用する UPN には文字、数字、ピリオド、ダッシュ、アンダースコアを含めることができますが、その他の種類の文字を含めることはできません。

代替 UPN サフィックスを Active Directory に追加する方法の詳細については、「ディレクトリ同期の準備 [」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=525430)。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. DS UPN AD UPN と一致Microsoft 365します。

ディレクトリ同期を既に設定している場合、Microsoft 365 のユーザーの UPN が、AD DS で定義されているユーザーの AD DS UPN と一致しない可能性があります。 ドメインが確認される前にユーザーにライセンスを割り当てた場合、この状況が発生することがあります。 これを修正するには[、PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730)を使用して重複する UPN を修正してユーザーの UPN を更新し、Microsoft 365 UPN が会社のユーザー名とドメインと一致する必要があります。 AD DS で UPN を更新し、Azure Active Directory ID と同期させる場合は、AD DS で変更を行う前に、Microsoft 365 でユーザーのライセンスを削除する必要があります。

また、「 [ディレクトリ同期用に、.local](prepare-a-non-routable-domain-for-directory-synchronization.md)ドメインなど、ルートできないドメインを準備する方法」も参照してください。

## <a name="next-steps"></a>次の手順

上記の手順 1 ~ 5 を実行した場合は、「ディレクトリ同期の [セットアップ」を参照してください](set-up-directory-synchronization.md)。
