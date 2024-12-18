# Vars

### `$TM_FILENAME_BASE$`

`capitalize(camelCase(fileNameWithoutExtension()))`

# Templates

## React

### `rsc`

```typescript jsx
import { ComponentPropsWithoutRef, FC, memo } from 'react';
import classNames from 'classnames';
import css from './$TM_FILENAME_BASE$.module.scss';


export type $TM_FILENAME_BASE$Props =
    {}
    & ComponentPropsWithoutRef<'div'>;

export const $TM_FILENAME_BASE$: FC<$TM_FILENAME_BASE$Props> = memo(function $TM_FILENAME_BASE$ (props) {
    const { className, ...other } = props;

    return (
        <div { ...other } className={ classNames(css.container, {}, [ className ]) }>
            $TM_FILENAME_BASE$ Component
        </div>
    );
});

```

### rsq

```typescript jsx
import type { QwikIntrinsicElements } from '@builder.io/qwik';
import { component$ } from '@builder.io/qwik';
import css from './$TM_FILENAME_BASE$.module.css';
import classNames from 'classnames';


export type $TM_FILENAME_BASE$Props =
    QwikIntrinsicElements['div']
    & {};

export const $TM_FILENAME_BASE$ = component$((props: $TM_FILENAME_BASE$Props) => {
    const { ...other } = props;

    return (
        <div
            { ...other }
            class={ classNames(css.container, {}, [ props.class ]) }
        >
            $TM_FILENAME_BASE$
        </div>
    );
});
```


## Types

### `tg`

```typescript
import {
    TypeGuard,
    TypeAssert,
    isObject,
    isString,
} from '@vanyamate/types-kit';


export type $TM_FILENAME_BASE$ = {
    field: string;
}

export const is$TM_FILENAME_BASE$: TypeGuard<$TM_FILENAME_BASE$> = function (data): data is $TM_FILENAME_BASE$ {
    return !(
        !isObject(data) ||
        !isString(data['field'])
    );
};

export const assert$TM_FILENAME_BASE$: TypeAssert<$TM_FILENAME_BASE$> = function (data, errorMessage) {
    if (!is$TM_FILENAME_BASE$(data)) {
        throw errorMessage(data);
    }
};
```