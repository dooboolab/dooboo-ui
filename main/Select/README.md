# Select

> `Select` dropdown conformed with `Item` component. Always useful to have a selectable list of items or values.
This component is made with react-native components and native styled components. 
All written in `typescript` ready to use cross-platforms (Web/ iOS/ Android).
The animation is powered by `react-native` Animated library.

<br/>

## Preview
| default | ChangeProps | Customized |   
|---------|-------------|------------|
|  ![default-select](https://user-images.githubusercontent.com/50701501/88159035-ba62c180-cc47-11ea-9a3b-dfe545a1c47b.gif) | ![changeprops-select](https://user-images.githubusercontent.com/50701501/88159072-c5b5ed00-cc47-11ea-808e-e548a3effaf3.gif)  | ![customized-select](https://user-images.githubusercontent.com/50701501/88159238-fd249980-cc47-11ea-9f94-b6fe1acb7bae.gif) |   

<br/>
<br/>
<br/>

## Installation

```sh
yarn add dooboo-ui
```

<br/>
<br/>
<br/>

## Getting started

### Import

```tsx
  import { Select, SelectItem } from 'dooboo-ui';
```

<br/>
<br/>
<br/>

### `Select` Props

| property         | necessary | types            | default             | description                                                     |
| -----------------| --------- | ---------------- | ------------------- | --------------------------------------------------------------- |
| testID           |           | string           |  -                  | for testing purposes                                            |
| opened           |           | boolean          |  false              | Controlled open state of dropdown                               |
| loading          |           | boolean          |  false              | Indicate loading state                                          |
| disabled         |           | boolean          |  false              | Whether disabled Select                                         |
| showArrow        |           | boolean          |  true               | Whether to show the drop-down arrow                             |
| bordered         |           | boolean          |  true               | Whether has border style                                        |
| activeOpacity    |           | number           |  .75                | Set the opacity when Item is pressed                            |
| listHeight       |           | number           |  (Auto-sized)       | Config popup height                                             |
| placeholder      |           | string or number |  -                  | Placeholder of select                                           | 
| value            |           | string or number |  -                  | Current selected option                                         |
| defaultValue     |           | string or number |  -                  | Initial selected option                                         |
| onSelect         |           | (value) => {}    |  -                  | Called when a Item is selected, the param is the `Item`'s value |
| onOpen           |           | (opened) => {}   |  -                  | Called when `Select` drop-down open or close                    |
| prefixIcon       |           | `ReactNode`      |  -                  | Custom prefix icon                                              |
| suffixIcon       |           | `ReactNode`      |  *`Arrow`           | Custom suffix icon, this replace default `Arrow`                |
| customLoader     |           | `ReactNode`      |  *`LoadingIndicator`| Custom loader, this replace default `Loader`                    |
| customStyle      |           | `ViewStyle`      |  -                  | Custom user styles, this applies for `Item`                     |
| customTextStyle  |           | `TextStyle`      |  -                  | Custom user styles, this applies for `Item`                     |

> * Default `Arrow` is the same element used in [dooboo-ui/accordion](https://github.com/dooboolab/dooboo-ui/tree/master/main/Accordion) and default `LoadingIndicator` is from [dooboo-ui/loadingIndicator](https://github.com/dooboolab/dooboo-ui/tree/master/main/LoadingIndicator)

<br/>
<br/>
<br/>

### `Item` Props

| property         | necessary | types                      | default              | description 
| -----------------| --------- | -------------------------- | -------------------- | ------------------------------------------- |
| value            | ???         | string or number           | -                    | Item value                                  |
| activeOpacity    |           | number                     | .75                  | This replace Select's                       |
| customStyle      |           | `ViewStyle`                | -                    | Custom user styles, this applies for `Item` |
| customTextStyle  |           | `TextStyle`                | -                    | Custom user styles, this applies for `Item` |

<br/>
<br/>
<br/>

## Usage

```tsx
import { Select, SelectItem } from 'dooboo-ui';
import styled from 'styled-components/native';


const CustomContainer = styled.View` 
  width: 100%;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
`;
const CustomSelectContainer = styled.View`
  width: 190px;
  height: 50px;
  align-items: center;
  justify-content: center;
`;

const Default = (): React.ReactElement => {
  
  const [selectedValue, onSelectedValue] = React.useState<string | number>();
  const [isOpen, toggleSelect] = React.useState<boolean>(false);

  return (
    <CustomContainer>
      <CustomSelectContainer>
        <Select
          opened={isOpen}
          loading={false}
          disabled={false}
          showArrow={true}
          bordered={true}
          activeOpacity={0.75}
          placeholder={'New fancy select'}
          value={selectedValue}
          onSelect={(value): void => onSelectedValue(value)}
          onOpen={(isOpen): void => toggleSelect(isOpen)}
          >
          <SelectItem value={'Item-1'}>{'Item-1'}</SelectItem>
          <SelectItem value={'Item-2'}>{'Item-2'}</SelectItem>
          <SelectItem value={'Item-3'}>{'Item-3'}</SelectItem>
        </Select>
      </CustomSelectContainer>
    </CustomContainer>
  );
};
```
