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
description: ディレクトリ同期を使用して Microsoft 365 にユーザーをプロビジョニングする準備方法と、このメソッドを使用する長期的な利点について説明します。
ms.openlocfilehash: 1fe99247a5c50c7bb8fc7eb1347ce6a4cd6aad94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927326"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

組織のハイブリッド ID とディレクトリ同期の利点は次のとおりです。

- 組織内の管理プログラムの削減
- 必要に応じてシングル サインオン シナリオを有効にする
- Microsoft 365 でのアカウント変更の自動化

ディレクトリ同期を使用する利点の詳細については [、「Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) とのハイブリッド ID」および [「Microsoft 365](plan-for-directory-synchronization.md)のハイブリッド ID」を参照してください。

ただし、ディレクトリ同期では、少なくともエラーが発生した Microsoft 365 サブスクリプションの Azure AD テナントと Active Directory ドメイン サービス (AD DS) が同期するように計画と準備が必要です。

最適な結果を得るには、次の手順に従います。

## <a name="1-directory-cleanup-tasks"></a>1. ディレクトリのクリーンアップ タスク

Ds を Azure ADテナントAD同期する前に、DS をクリーンアップするADがあります。

> [!IMPORTANT]
> 同期する前に DS クリーンアップAD実行しない場合、展開プロセスに大きな悪影響を及ぼす可能性があります。 ディレクトリ同期、エラーの特定、および再同期のサイクルを実行するには、数日または数週間かかる場合があります。

MICROSOFT AD DS で、Microsoft 365 ライセンスが割り当てられる各ユーザー アカウントに対して、次のクリーンアップ タスクを実行します。

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

DS と Microsoft 365 ADディレクトリ同期を成功するには、DS 属性を適切にADする必要があります。 たとえば、Microsoft 365 環境と同期されている特定の属性で特定の文字が使用されない必要があります。 予期しない文字を使用すると、ディレクトリ同期は失敗しませんが、警告が返される可能性があります。 無効な文字を指定すると、ディレクトリ同期が失敗します。

また、一部の DS ユーザーが 1 つ以上の重複AD場合、ディレクトリ同期は失敗します。 各ユーザーは、一意の属性を持っている必要があります。

準備する必要がある属性を次に示します。

- **displayName**

  - 属性がユーザー オブジェクトに存在する場合は、Microsoft 365 と同期されます。
  - この属性がユーザー オブジェクトに存在する場合は、その属性の値が必要です。 つまり、属性を空白にすることはできません。
  - 最大文字数: 256

- **givenName**

  - 属性がユーザー オブジェクトに存在する場合、その属性は Microsoft 365 と同期されますが、Microsoft 365 ではその属性を必要としたり使用したりしません。
  - 最大文字数: 64

- **mail**

  - 属性値はディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 重複する値がある場合は、値を持つ最初のユーザーが同期されます。 以降のユーザーは Microsoft 365 には表示されません。 両方のユーザーが Microsoft 365 に表示するには、Microsoft 365 の値を変更するか、AD DS の両方の値を変更する必要があります。

- **mailNickname** (Exchange エイリアス)

  - 属性値はピリオド (.) で始めできません。
  - 属性値はディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 同期名のアンダースコア ("_") は、この属性の元の値に無効な文字が含まれているかどうかを示します。 この属性の詳細については、「Exchange alias 属性 [」を参照してください](/powershell/module/exchange/set-mailbox)。
    >

- **proxyAddresses**

  - 複数値属性
  - 値あたりの最大文字数: 256
  - 属性値にはスペースを含めずに指定してください。
  - 属性値はディレクトリ内で一意である必要があります。
  - 無効な文字: \< \> ( ) ; , , [ ] " '

    無効な文字は、型の区切り文字と ":"に続く文字に適用され、SMTP:User@contso.com が許可されますが、SMTP:user:M@contoso.com されません。

    > [!IMPORTANT]
    > すべての簡易メール トランスポート プロトコル (SMTP) アドレスは、電子メール メッセージングの標準に準拠している必要があります。 重複アドレスまたは不要なアドレスが存在する場合は削除します。

- **sAMAccountName**

  - 最大文字数: 20
  - 属性値はディレクトリ内で一意である必要があります。
  - 無効な文字: [ \ " | 、 / : \< \> + = ; ? \* ']
  - ユーザーが無効な **sAMAccountName** 属性を持ち、有効な **userPrincipalName** 属性を持つ場合、ユーザー アカウントは Microsoft 365 で作成されます。
  - **sAMAccountName と** **userPrincipalName** の両方が無効な場合は、AD DS **userPrincipalName** 属性を更新する必要があります。

- **sn** (姓)

  - 属性がユーザー オブジェクトに存在する場合、その属性は Microsoft 365 と同期されますが、Microsoft 365 ではその属性を必要としたり使用したりしません。

- **targetAddress**

    ユーザーに対して設定された **targetAddress** 属性 (SMTP:tom@contoso.com など) が Microsoft 365 GAL に表示されている必要があります。 サード パーティ製のメッセージング移行シナリオでは、MICROSOFT 365 スキーマ拡張機能が DS にADされます。 Microsoft 365 スキーマ拡張機能は、DS からディレクトリ同期ツールを使用して設定される Microsoft 365 オブジェクトを管理するために、他の有用な属性ADします。 たとえば、非表示のメールボックスまたは配布グループを管理するための **msExchHideFromAddressLists** 属性が追加されます。

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

Active Directory は、組織内のエンド ユーザーが **sAMAccountName** または **userPrincipalName** を使用してディレクトリにサインインするように設計されています。 同様に、エンド ユーザーは、自分の仕事または学校のアカウントのユーザー プリンシパル名 (UPN) を使用して Microsoft 365 にサインインできます。 ディレクトリ同期は、Azure Active Directory 内の新しいユーザーの作成を試み、DS 内の UPN と同じ UPN をADします。 UPN は電子メール アドレスのように書式設定されます。

Microsoft 365 では、UPN は電子メール アドレスの生成に使用される既定の属性です。 **userPrincipalName** (AD DS および Azure AD) と **proxyAddresses** のプライマリ 電子メール アドレスを異なる値に設定するのは簡単です。 異なる値に設定すると、管理者とエンド ユーザーが混乱する可能性があります。

これらの属性を揃えて混乱を減らすのが最善の方法です。 Active Directory フェデレーション サービス (AD FS) 2.0 でのシングル サインオンの要件を満たすには、Azure Active Directory の UPN と AD DS が一致し、有効なドメイン名前空間を使用していることを確認する必要があります。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. DS に代替 UPN サフィックスをADする

ユーザーの会社の資格情報を Microsoft 365 環境に関連付けるには、代替 UPN サフィックスを追加する必要がある場合があります。 UPN サフィックスは、@ 文字の右側の UPN の一部です。 シングル サインオンに使用する UPN には文字、数字、ピリオド、ダッシュ、アンダースコアを含めることができますが、その他の種類の文字を含めることはできません。

代替 UPN サフィックスを Active Directory に追加する方法の詳細については、「ディレクトリ同期の準備 [」を参照してください]( https://go.microsoft.com/fwlink/p/?LinkId=525430)。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. DS UPN AD Microsoft 365 UPN と一致する

ディレクトリ同期を既に設定している場合、Microsoft 365 のユーザーの UPN が、AD DS で定義されているユーザーの AD DS UPN と一致しない可能性があります。 ドメインが確認される前にユーザーにライセンスを割り当てた場合、この状況が発生することがあります。 これを修正するには [、PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730) を使用して重複する UPN を修正してユーザーの UPN を更新し、Microsoft 365 UPN が企業のユーザー名とドメインと一致します。 AD DS で UPN を更新し、Azure Active Directory ID と同期させる場合は、AD DS で変更を行う前に、Microsoft 365 でユーザーのライセンスを削除する必要があります。

また、「 [ディレクトリ同期用に、.local](prepare-a-non-routable-domain-for-directory-synchronization.md)ドメインなど、ルートできないドメインを準備する方法」も参照してください。

## <a name="next-steps"></a>次の手順

上記の手順 1 ~ 5 を実行した場合は、「ディレクトリ同期の [セットアップ」を参照してください](set-up-directory-synchronization.md)。